---
title: "컴파일러 오류 C2259 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2259"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2259"
ms.assetid: e458236f-bdea-4786-9aa6-a98d8bffa5f4
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2259
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 추상 클래스를 인스턴스화할 수 없습니다.  
  
 코드가 추상 클래스 또는 구조체의 인스턴스를 선언합니다.  
  
 하나 이상의 순수 가상 함수를 사용하여 클래스나 구조체를 인스턴스화할 수 없습니다.  파생 클래스의 개체를 인스턴스화하려면 파생 클래스가 각 순수 가상 함수를 재정의해야 합니다.  
  
 자세한 내용은 [암시적 추상 클래스](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Implicitly_abstract_classes)를 참조하십시오.  
  
 다음 샘플에서는 C2259 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2259.cpp  
// compile with: /c  
class V {  
public:  
   void virtual func() = 0;  
};  
class A : public V {};  
class B : public V {  
public:  
   void func();  
};  
V v;  // C2259, V is an abstract class  
A a;  // C2259, A inherits func() as pure virtual  
B b;  // OK, B defines func()  
```  
  
 인터페이스를 통해 파생된 클래스에서 public 이외의 액세스 권한을 사용하여 인터페이스 메서드를 구현할 때마다 C2259가 발생합니다.  파생 클래스에서 구현된 인터페이스 메서드에는 public 액세스 권한이 있어야 하기 때문입니다.  액세스 권한이 더 제한적인 인터페이스에 대해 멤버 함수를 구현하는 경우 컴파일러는 이러한 함수가 인터페이스에 정의된 인터페이스 메서드에 대해 구현되는 것으로 간주하지 않으므로 파생 클래스가 추상 클래스가 됩니다.  
  
 이 문제를 해결하는 데는 두 가지 방법이 있습니다.  
  
-   구현된 메서드에 대한 액세스 권한을 public으로 설정합니다.  
  
-   파생 클래스에서 구현된 인터페이스 메서드에 대해 범위 결정 연산자를 사용하여 구현된 메서드 이름을 인터페이스 이름으로 한정합니다.  
  
 C2259 오류는 Visual C\+\+ 2005에 대해 적용되었으며, 이제 **\/Zc:wchar\_t**가 기본적으로 설정된다는 컴파일러 규칙의 결과로 발생할 수도 있습니다.  이 경우 C2599는 이전 버전의 동작을 활용할 수 있도록 **\/Zc:wchar\_t\-**를 사용하여 컴파일하거나 형식이 호환되도록 업데이트하여 해결할 수 있습니다.  자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)을 참조하십시오.  
  
 다음 샘플에서는 C2259 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2259b.cpp  
// compile with: /c  
#include <windows.h>   
  
class MyClass {  
public:  
   // WCHAR now typedef'ed to wchar_t  
   virtual void func(WCHAR*) = 0;  
};  
  
class MyClass2 : MyClass {  
public:  
   void func(unsigned short*);  
};  
  
MyClass2 x;   // C2259  
  
// OK  
class MyClass3 {  
public:  
   virtual void func(WCHAR*) = 0;  
   virtual void func2(wchar_t*) = 0;  
   virtual void func3(unsigned short*) = 0;  
};  
  
class MyClass4 : MyClass3 {  
public:  
   void func(WCHAR*) {}  
   void func2(wchar_t*) {}  
   void func3(unsigned short*) {}  
};  
  
MyClass4 y;  
```  
  
 다음 샘플에서는 C2259 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2259c.cpp  
// compile with: /clr  
interface class MyInterface {  
   void MyMethod();  
};  
  
ref class MyDerivedClass: public MyInterface {  
private:  
   // Uncomment the following line to resolve.  
   // public:  
   void MyMethod(){}  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass^ instance = gcnew MyDerivedClass; // C2259  
}  
```  
  
 다음 샘플에서는 C2259 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2259d.cpp  
// compile with: /clr:oldSyntax  
public __gc __interface MyInterface {  
   void MyMethod();  
};  
  
__gc class MyDerivedClass : public MyInterface {  
// Uncomment the following line to resolve.  
// public:  
   void MyMethod() {};  
   // or the following line  
   // void MyInterface::MyMethod() {};  
};  
  
int main() {  
   MyDerivedClass *instance = new MyDerivedClass();   // C2259  
}  
```