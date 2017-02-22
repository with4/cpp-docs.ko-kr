---
title: "일반 규칙 및 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 일반 규칙 및 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
  
-   **dllimport** 또는 `dllexport` 특성을 사용하지 않고 함수 또는 개체를 선언하면 해당 함수 또는 개체가 DLL 인터페이스의 일부분으로 간주되지 않습니다.  따라서 해당 모듈 또는 같은 프로그램의 다른 모듈에 함수 또는 개체의 정의가 있어야 합니다.  함수 또는 개체를 DLL 인터페이스에 포함하려면 다른 모듈에서 함수 또는 개체의 정의를 `dllexport`로 선언해야 합니다.  그렇게 하지 않으면 링커 오류가 생성됩니다.  
  
     `dllexport` 특성을 사용하여 함수 또는 개체를 선언하면 해당 정의가 같은 프로그램의 일부 모듈에 나타나야 합니다.  그렇게 하지 않으면 링커 오류가 생성됩니다.  
  
-   프로그램의 모듈 하나에 동일 함수 또는 개체에 대한 **dllimport** 선언과 `dllexport` 선언이 모두 포함되어 있으면 `dllexport` 특성이 **dllimport** 특성보다 우선적으로 사용됩니다.  그러나 이 경우 컴파일러 경고가 생성됩니다.  예를 들면 다음과 같습니다.  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   C\+\+에서는 **dllimport** 특성을 사용하여 선언된 데이터 개체의 주소로 전역으로 선언된 데이터 포인터 또는 정적 로컬 데이터 포인터를 초기화할 수 있습니다\(C에서 오류 발생\).  또한 **dllimport** 특성을 사용하여 선언된 함수의 주소로 정적 로컬 함수 포인터를 초기화할 수 있습니다.  C에서는 이러한 대입으로 인해 포인터가 함수의 주소 대신 DLL 가져오기 썽크\(함수로 제어를 전송하는 코드 스텁\)의 주소로 설정됩니다.  C\+\+에서는 포인터가 함수의 주소로 설정됩니다.  예를 들면 다음과 같습니다.  
  
    ```  
    __declspec( dllimport ) void func1( void );  
    __declspec( dllimport ) int i;  
  
    int *pi = &i;                             // Error in C  
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,  
                                              // function in C++  
  
    void func2()  
    {  
       static int *pi = &i;                  // Error in C  
       static void ( *pf )( void ) = &func1; // Address of thunk in C,  
                                             // function in C++  
    }  
    ```  
  
     그러나 개체의 선언에 `dllexport` 특성을 포함하는 프로그램은 프로그램의 어딘가에 해당 개체의 정의를 제공해야 하므로 `dllexport` 함수의 주소로 전역 또는 로컬 정적 함수 포인터를 초기화할 수 있습니다.  마찬가지로 `dllexport` 데이터 개체의 주소로 전역 또는 로컬 정적 데이터 포인터를 초기화할 수 있습니다.  예를 들어, 다음 코드는 C 또는 C\+\+에서 오류를 발생시키지 않습니다.  
  
    ```  
    __declspec( dllexport ) void func1( void );  
    __declspec( dllexport ) int i;  
  
    int *pi = &i;                              // Okay  
    static void ( *pf )( void ) = &func1;      // Okay  
  
    void func2()  
    {  
        static int *pi = &i;                   // Okay  
        static void ( *pf )( void ) = &func1;  // Okay  
    }  
    ```  
  
-   일반 클래스와 클래스 템플릿의 특수화 간에 `dllexport`를 보다 일관성 있게 적용할 수 있도록 Visual C\+\+ .NET의 동작이 변경되어 `dllexport`로 표시되지 않은 기본 클래스가 있는 일반 클래스에 `dllexport`를 적용하면 컴파일러가 C4275를 생성합니다.  
  
     컴파일러는 기본 클래스가 클래스 템플릿의 특수화인 경우 동일한 경고를 생성합니다.  이 문제를 해결하려면 기본 클래스를 `dllexport`로 표시하십시오.  클래스 템플릿 특수화의 문제점은 **\_\_declspec\(dllexport\)**를 어디에 배치할 것인가입니다. 클래스 템플릿은 표시할 수 없습니다.  대신 명시적으로 클래스 템플릿을 인스턴스화하고 이 명시적 인스턴스화를 `dllexport`로 표시합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     템플릿 인수가 파생 클래스일 경우 이 해결 방법은 실패합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     이것은 템플릿의 공통 패턴이므로 하나 이상의 기본 클래스가 있는 클래스에 적용될 때 및 하나 이상의 기본 클래스가 클래스 템플릿의 특수화일 때 컴파일러가 `dllexport`의 의미 체계를 변경했습니다.  이 경우 컴파일러는 암시적으로 `dllexport`를 클래스 템플릿의 특수화에 적용합니다.  Visual C\+\+ .NET에서는 사용자가 경고를 받지 않고 다음을 수행할 수 있습니다.  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)