---
title: "복사 생성자 및 복사 할당 연산자(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 연산자, 개체 복사"
  - "값을 할당하여 개체 복사"
  - "할당 연산자, 개체 복사용"
  - "대입문, 개체 복사"
  - "개체 복사"
  - "개체 초기화, 개체 복사"
  - "개체[C++], 복사"
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 복사 생성자 및 복사 할당 연산자(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  C\+\+11부터 언어에서 *복사 할당* 및 *이동 할당*이라는 두 가지 할당이 지원됩니다.  이 문서에서 별도로 명시하지 않는 한 "할당"은 복사 할당을 의미합니다.  이동 할당에 대한 자세한 내용은 [이동 생성자 및 이동 할당 연산자\(C\+\+\)](http://msdn.microsoft.com/ko-kr/1442de5f-37a5-42a1-83a6-ec9cfe0414db)를 참조하세요.  
>   
>  할당 작업과 초기화 작업은 모두 개체를 복사합니다.  
  
-   **할당**: 한 개체의 값이 다른 개체에 할당하면 첫 번째 개체를 두 번째 개체에 복사합니다.  따라서  
  
    ```cpp  
    Point a, b;  
    ...  
    a = b;  
    ```  
  
     `b`의 값이 `a`에 복사되도록 합니다.  
  
-   **초기화**: 새 개체를 선언하거나, 인수를 함수에 값으로 전달하거나, 값이 함수에서 값으로 반환될 때 초기화가 발생합니다.  
  
 클래스 형식의 개체에 대해 "복사"의 의미를 정의할 수 있습니다.  예를 들어 다음 코드를 고려합니다.  
  
```cpp  
TextFile a, b;  
a.Open( "FILE1.DAT" );  
b.Open( "FILE2.DAT" );  
b = a;  
```  
  
 앞의 코드는 "FILE1.DAT의 내용을 FILE2.DAT에 복사"를 의미하거나, "FILE2.DAT를 무시하고 `b`를 FILE1.DAT의 두 번째 핸들로 만들기"를 의미할 수도 있습니다. 다음과 같이 각 클래스에 적절한 복사 의미를 연결해야 합니다.  
  
-   참조와 함께 클래스 형식에 반환 형식으로 할당 연산자 `operator=`을 사용하고, 예를 들어 `const` 등 `ClassName& operator=(const ClassName& x);` 참조를 전달하는 매개 변수를 사용합니다.  
  
-   복사 생성자를 사용합니다.  복사 생성자에 대한 자세한 내용은 [생성자를 선언하기 위한 규칙](../misc/rules-for-declaring-constructors.md)을 참조하세요.  
  
 복사 생성자를 선언하지 않으면 컴파일러는 자동으로 멤버 단위 복사 생성자를 생성합니다.  복사 할당 연산자를 선언하지 않으면 컴파일러는 자동으로 멤버 단위 복사 할당 연산자를 생성합니다. 복사 생성자의 선언은 컴파일러에서 생성된 복사 할당 연산자를 숨기지 않으며 그 반대의 경우에도 마찬가지입니다.  둘 중 하나를 구현하는 경우 다른 하나도 구현하여 코드의 의미를 분명히 하는 것이 좋습니다.  
  
 멤버 단위 할당에 대한 자세한 내용은 [\(NOTINBUILD\) Memberwise Assignment and Initialization](http://msdn.microsoft.com/ko-kr/94048213-8b49-4416-8069-b1b7a6f271f9)를 참조하세요.  
  
 복사 생성자는 *class\-name*이 생성자가 정의된 클래스의 이름인 형식 *class\-name***&**의 인수를 사용합니다.  예:  
  
```cpp  
// spec1_copying_class_objects.cpp  
class Window  
{  
public:  
    Window( const Window& ); // Declare copy constructor.  
    // ...  
};  
  
int main()  
{  
}  
```  
  
> [!NOTE]
>  가능할 때마다 복사 생성자의 인수 *const class\-name***&**의 형식을 만듭니다.  이는 복사 생성자가 복사 중인 개체를 실수로 변경하는 것을 방지합니다.  **const** 개체에서도 복사할 수 있습니다.  
  
## 컴파일러에서 생성된 복사 생성자  
 사용자 정의 복사 생성자와 같이 컴파일러에서 생성된 복사 생성자에는 "*class\-name*에 대한 형식 참조"의 단일 인수가 있습니다. 한 가지 예외는 형식 **const** *class\-name***&**의 단일 인수로 사용할 때 모든 기본 클래스와 멤버 클래스에서 복사 생성자를 선언하는 경우입니다.  이런 경우 컴파일러에서 생성된 복사 생성자의 인수는 **const**이기도 합니다.  
  
 복사 생성자에 대한 인수 형식이 **const**가 아닌 경우, **const** 개체를 복사하여 초기화하면 오류가 생성됩니다.  인수가 **const**이면 **const**가 아닌 개체를 복사하여 초기화할 수 있지만 반대의 경우는 불가능합니다.  
  
 컴파일러에서 생성된 할당 연산자는 **const**와 관련된 동일한 패턴을 따릅니다. 모든 기본 및 멤버 클래스의 할당 연산자 형식이 **const** *class\-name&.*이 아닌 경우 *class\-name***&** 형식의 단일 인수를 사용합니다. 이 경우 클래스의 생성된 할당 연산자는 **const** 인수를 사용합니다.  
  
> [!NOTE]
>  가상 기본 클래스가 복사 생성자에 의해 초기화되고 컴파일러에서 생성되거나 사용자 정의되는 경우 생성되는 시점에 한 번만 초기화됩니다.  
  
 의미는 복사 생성자의 의미와 비슷합니다.  인수 형식이 **const**가 아닐 경우 **const** 개체의 할당이 오류를 생성합니다.  **const** 값이 **const**가 아닌 값에 할당될 수 있지만 반대의 경우는 불가능합니다.  
  
 오버로드된 할당 연산자에 대한 자세한 내용은 [할당](../cpp/assignment.md)을 참조하세요.  
  
## 참고 항목  
 [특수 멤버 함수](../misc/special-member-functions-cpp.md)