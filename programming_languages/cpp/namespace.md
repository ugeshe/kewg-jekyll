# Namespace

## Example
1. Using cout in std library without using `using namespace std`.

```c++
#include <iostream>

int main(){

std::cout << "Hello world" << std::endl;
return 0;
}

```

2. Using cout in std library using `using namespace std`.

```c++
#include <iostream>

using namespace std;

int main(){

cout << "Hello world" << endl;
return 0;
}

```

3. Uisng `cout` and `endl`. Here we define the scope of `cout` **explicitly**.

```c++
#include <iostream>

using std::cout;

int main(){

/* 
    As you can see here we used cout without std:: scope
    while we are using endl with std:: scope
*/
   
cout << "Hello world" std::endl;
return 0;
}

```
