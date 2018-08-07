---
title: 템플릿 Friend | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 077acea5-0d0f-4b33-916d-1211797e5e28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97447189419bad8d3ad6f2026a7ee5f701ebca04
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466958"
---
# <a name="template-friends"></a>템플릿 friend

클래스 템플릿 있을 수 있습니다 [친구](friend-cpp.md)합니다. 클래스 또는 클래스 템플릿, 함수 또는 함수 템플릿은 템플릿 클래스에 대한 friend일 수 있습니다. friends는 클래스 템플릿 또는 함수 템플릿의 특수화가 될 수도 있지만 부분 특수화는 될 수 없습니다.  
  
**C + + 11**: 양식을 사용 하 여 형식 매개 변수는 friend로 선언할 수 있습니다 `friend T;`합니다.  
  
```cpp
template <typename T>  
class my_class  
{  
    friend T;  
    //...  
};  
```  
  
## <a name="example"></a>예

다음 예제에서 friend 함수는 클래스 템플릿 내에서 함수 템플릿으로 정의됩니다. 이 코드는 모든 템플릿 인스턴스화에 대한 friend 함수 버전을 만듭니다. 이 구문은 사용자의 friend 함수가 클래스와 같은 템플릿 매개 변수로 결정될 경우 유용합니다.  
  
```cpp
// template_friend1.cpp  
// compile with: /EHsc  
  
#include <iostream>  
using namespace std;  
  
template <class T> class Array {  
   T* array;  
   int size;  
  
public:  
   Array(int sz): size(sz) {  
      array = new T[size];  
      memset(array, 0, size * sizeof(T));  
   }  
  
   Array(const Array& a) {  
      size = a.size;  
      array = new T[size];  
      memcpy_s(array, a.array, sizeof(T));  
   }  
  
   T& operator[](int i) {  
      return *(array + i);  
   }  
  
   int Length() { return size; }  
  
   void print() {  
      for (int i = 0; i < size; i++)        
         cout << *(array + i) << " ";  
  
      cout << endl;  
   }  
  
   template<class T>  
   friend Array<T>* combine(Array<T>& a1, Array<T>& a2);  
};  
  
template<class T>  
Array<T>* combine(Array<T>& a1, Array<T>& a2) {  
   Array<T>* a = new Array<T>(a1.size + a2.size);  
   for (int i = 0; i < a1.size; i++)  
      (*a)[i] = *(a1.array + i);  
  
   for (int i = 0; i < a2.size; i++)  
      (*a)[i + a1.size] = *(a2.array + i);  
  
   return a;  
}  
  
int main() {  
   Array<char> alpha1(26);  
   for (int i = 0 ; i < alpha1.Length() ; i++)  
      alpha1[i] = 'A' + i;  
  
   alpha1.print();  
  
   Array<char> alpha2(26);  
   for (int i = 0 ; i < alpha2.Length() ; i++)  
      alpha2[i] = 'a' + i;  
  
   alpha2.print();  
   Array<char>*alpha3 = combine(alpha1, alpha2);  
   alpha3->print();  
   delete alpha3;  
}  
```  
  
```Output
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z   
a b c d e f g h i j k l m n o p q r s t u v w x y z   
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z a b c d e f g h i j k l m n o p q r s t u v w x y z   
```  
  
## <a name="example"></a>예  

다음 예제에서는 템플릿 특수화를 가진 friend를 다룹니다. 원본 함수 템플릿이 friend인 경우 함수 템플릿 특수화는 자동으로 friend입니다.  
  
또한 다음 코드의 friend 선언 앞의 주석이 나타내는 것처럼 템플릿의 특수화 버전만 friend로 선언할 수 있습니다. 이렇게 하면 friend 템플릿 특수화 정의를 템플릿 클래스 외부에 배치해야 합니다.  
  
```cpp
// template_friend2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
class Array;  
  
template <class T>  
void f(Array<T>& a);  
  
template <class T> class Array  
{  
    T* array;  
    int size;  
  
public:  
    Array(int sz): size(sz)  
    {  
        array = new T[size];  
        memset(array, 0, size * sizeof(T));  
    }  
    Array(const Array& a)  
    {  
        size = a.size;  
        array = new T[size];  
        memcpy_s(array, a.array, sizeof(T));  
    }  
    T& operator[](int i)  
    {  
        return *(array + i);  
    }  
    int Length()  
    {   
        return size;  
    }  
    void print()  
    {  
        for (int i = 0; i < size; i++)  
        {  
            cout << *(array + i) << " ";  
        }  
        cout << endl;  
    }  
    // If you replace the friend declaration with the int-specific  
    // version, only the int specialization will be a friend.  
    // The code in the generic f will fail  
    // with C2248: 'Array<T>::size' :  
    // cannot access private member declared in class 'Array<T>'.  
    //friend void f<int>(Array<int>& a);  
  
    friend void f<>(Array<T>& a);  
};  
  
// f function template, friend of Array<T>  
template <class T>  
void f(Array<T>& a)  
{  
    cout << a.size << " generic" << endl;  
}  
  
// Specialization of f for int arrays  
// will be a friend because the template f is a friend.  
template<> void f(Array<int>& a)  
{  
    cout << a.size << " int" << endl;  
}  
  
int main()  
{  
    Array<char> ac(10);  
    f(ac);  
  
    Array<int> a(10);  
    f(a);  
}  
```  

```Output
10 generic  
10 int  
```  
  
## <a name="example"></a>예  
 
다음 예제에서는 클래스 템플릿 내에 선언된 friend 클래스 템플릿을 보여 줍니다. 클래스 템플릿은 friend 클래스의 템플릿 인수로 사용됩니다. friend 클래스 템플릿은 선언된 클래스 템플릿의 외부에 정의되어야 합니다. 또한 friend 템플릿의 모든 특수화 또는 부분 특수화는 원본 클래스 템플릿의 friend입니다.  
  
```cpp  
// template_friend3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T>  
class X  
{  
private:  
   T* data;  
   void InitData(int seed) { data = new T(seed); }  
public:  
   void print() { cout << *data << endl; }  
   template <class U> friend class Factory;  
};  
  
template <class U>  
class Factory  
{  
public:  
   U* GetNewObject(int seed)  
   {  
      U* pu = new U;  
      pu->InitData(seed);  
      return pu;  
   }  
};  
  
int main()  
{  
   Factory< X<int> > XintFactory;  
   X<int>* x1 = XintFactory.GetNewObject(65);  
   X<int>* x2 = XintFactory.GetNewObject(97);  
  
   Factory< X<char> > XcharFactory;  
   X<char>* x3 = XcharFactory.GetNewObject(65);  
   X<char>* x4 = XcharFactory.GetNewObject(97);  
   x1->print();  
   x2->print();  
   x3->print();  
   x4->print();  
}  
```  

```Output 
65  
97  
A  
a  
```  
  
## <a name="see-also"></a>참고자료  
 [기본 인수](../cpp/default-arguments.md)