---
Title: Data Structures & Algorithm Lecture 4
Status: 
marker:
  - "[[btech]]"
  - "[[Algorithm]]"
  - "[[Stack]]"
  - "[[Array]]"
tags: 
Date: 2024.07.26
Time: 09:29
---

# Data Structures & Algorithm Lecture 4
###### Information
- date: 2024.07.26
- time: 09:29

# Index
- [Performance and Limitations](#performance-and-limitations)
  - [Performance](#performance)
  - [Limitations](#limitations)
- [Advantages](#advantages)
  - [Reversal of an Array Using Stack](#reversal-of-an-array-using-stack)
  - [Decimal to Binary Conversion](#decimal-to-binary-conversion)
  - [Parenthesis Matching](#parenthesis-matching)
  - [HTML Tag Matching](#html-tag-matching)
  - [Conversion of Arithmetic Expressions](#conversion-of-arithmetic-expressions)
  - [Evaluation of Arithmetic Expressions](#evaluation-of-arithmetic-expressions)
  - [Traversal Algorithm](#traversal-algorithm)
- [Function Invocations](#function-invocations)
  - [Recursion](#recursion)

# Content

## Performance and Limitations 
### Performance
- Let n be the number of elements in the stack 
- The space used is `O(n)`
- Each operation runs in constant time, O(1)

### Limitations
- The maximum size of the stack must be defined a priori and can't be changed
- Trying to push a new element into a full stack causes an implementation-specific error

## Advantages 

### Reversal of an Array Using Stack

#### What We Are Trying to Do
We are trying to reverse an array using a stack for efficient memory management.

#### Process
First, push all the elements to a stack using a loop. For example, with `A[5] = {1,2,3,4,5}`:

```cpp
#include <stack>
#include <iostream>

int main() {
    int a[5] = {1, 2, 3, 4, 5};
    std::stack<int> s;
    for (int i = 0; i < 5; i++) {
        s.push(a[i]);
    }

    int i = 0;
    while (!s.empty()) {
        a[i++] = s.top();
        s.pop();
    }

    for (int i = 0; i < 5; i++) {
        std::cout << a[i] << " ";
    }

    return 0;
}
```

### Decimal to Binary Conversion
##### What We Are Trying to Do
Convert a decimal number into binary by dividing the number by two and storing the remainder.

##### Process
```cpp
#include <stack>
#include <iostream>

int main() {
    int dec = 256;
    std::stack<int> s;

    while (dec > 0) {
        int digit = dec % 2;
        s.push(digit);
        dec /= 2;
    }

    while (!s.empty()) {
        std::cout << s.top();
        s.pop();
    }

    return 0;
}
```

### Parenthesis Matching
##### What We Are Doing
- Checking if each opening parenthesis has a corresponding closing parenthesis.
- Ensuring the number of opening and closing parentheses match.
- Detecting mismatched parentheses.

##### Solution
```cpp
#include <iostream>
#include <stack>
#include <map>

bool isBalanced(const std::string& expr) {
    std::stack<char> s;
    std::map<char, char> par = {{')', '('}, {']', '['}, {'}', '{'}, {'>', '<'}};
    std::string open = "([{<";

    for (char ch : expr) {
        if (open.find(ch) != std::string::npos) {
            s.push(ch);
        } else if (par.find(ch) != par.end()) {
            if (s.empty() || s.top() != par[ch]) {
                return false;
            }
            s.pop();
        }
    }

    return s.empty();
}

int main() {
    std::string expr;
    std::cout << "Enter the string to check for balancing: ";
    std::cin >> expr;

    if (isBalanced(expr)) {
        std::cout << "Balanced\n";
    } else {
        std::cout << "Not Balanced\n";
    }

    return 0;
}
```

### HTML Tag Matching
##### What We Are Doing
Checking if HTML tags are properly nested and matched.

##### Solution
```cpp
#include <iostream>
#include <stack>
#include <string>

bool isHTMLBalanced(const std::string& html) {
    std::stack<std::string> s;
    size_t pos = 0;

    while (pos < html.size()) {
        if (html[pos] == '<') {
            size_t end = html.find('>', pos);
            if (end == std::string::npos) {
                return false;
            }

            std::string tag = html.substr(pos, end - pos + 1);
            if (tag[1] != '/') {
                s.push(tag);
            } else {
                if (s.empty() || s.top().substr(1) != tag.substr(2)) {
                    return false;
                }
                s.pop();
            }
            pos = end + 1;
        } else {
            pos++;
        }
    }

    return s.empty();
}

int main() {
    std::string html;
    std::cout << "Enter the HTML string to check for balancing: ";
    std::cin >> html;

    if (isHTMLBalanced(html)) {
        std::cout << "Balanced\n";
    } else {
        std::cout << "Not Balanced\n";
    }

    return 0;
}
```

### Conversion of Arithmetic Expressions
##### Infix to Postfix Conversion

```cpp
#include <iostream>
#include <stack>
#include <string>

int precedence(char op) {
    if (op == '+' || op == '-') return 1;
    if (op == '*' || op == '/') return 2;
    return 0;
}

std::string infixToPostfix(const std::string& infix) {
    std::stack<char> s;
    std::string postfix;

    for (char ch : infix) {
        if (isdigit(ch)) {
            postfix += ch;
        } else if (ch == '(') {
            s.push(ch);
        } else if (ch == ')') {
            while (!s.empty() && s.top() != '(') {
                postfix += s.top();
                s.pop();
            }
            s.pop();
        } else {
            while (!s.empty() && precedence(s.top()) >= precedence(ch)) {
                postfix += s.top();
                s.pop();
            }
            s.push(ch);
        }
    }

    while (!s.empty()) {
        postfix += s.top();
        s.pop();
    }

    return postfix;
}

int main() {
    std::string infix = "3+(2*4)-5";
    std::cout << "Postfix: " << infixToPostfix(infix) << std::endl;

    return 0;
}
```

### Evaluation of Arithmetic Expressions
##### Evaluating Postfix Expression

```cpp
#include <iostream>
#include <stack>
#include <string>

int evaluatePostfix(const std::string& postfix) {
    std::stack<int> s;

    for (char ch : postfix) {
        if (isdigit(ch)) {
            s.push(ch - '0');
        } else {
            int val2 = s.top(); s.pop();
            int val1 = s.top(); s.pop();
            switch (ch) {
                case '+': s.push(val1 + val2); break;
                case '-': s.push(val1 - val2); break;
                case '*': s.push(val1 * val2); break;
                case '/': s.push(val1 / val2); break;
            }
        }
    }

    return s.top();
}

int main() {
    std::string postfix = "324*+5-";
    std::cout << "Result: " << evaluatePostfix(postfix) << std::endl;

    return 0;
}
```

### Traversal Algorithm
##### DFS Traversal using Stack

```cpp
#include <iostream>
#include <stack>
#include <vector>

void DFS(int start, const std::vector<std::vector<int>>& adj) {
    std::vector<bool> visited(adj.size(), false);
    std::stack<int> s;
    s.push(start);

    while (!s.empty()) {
        int node = s.top();
        s.pop();

        if (!visited[node]) {
            visited[node] = true;
            std::cout << node << " ";
            
            for (int neighbor : adj[node]) {
                if (!visited[neighbor]) {
                    s.push(neighbor);
                }
            }
        }
    }
}

int main() {
    std::vector<std::vector<int>> adj = {
        {1, 2},
        {0, 3, 4},
        {0, 5, 6},
        {1},
        {1},
        {2},
        {2}
    };

    DFS(0, adj);

    return 0;
}
```

## Function Invocations
### Recursion
Recursion is a function calling itself directly or indirectly to solve a problem. It can be used in various algorithms such as tree traversals, sorting, and more.

## Infix Prefix Postfix Expressions
