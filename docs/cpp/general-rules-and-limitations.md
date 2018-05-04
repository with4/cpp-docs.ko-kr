---
title: 일반 규칙 및 제한 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 218bd2fb58ccc4d3a3c2e1d297be930350577d18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="general-rules-and-limitations"></a>일반 규칙 및 제한 사항
## <a name="microsoft-specific"></a>Microsoft 전용  
  
-   함수 선언 또는 하지 않고 개체는 **dllimport** 또는 `dllexport` 특성, 함수 또는 개체가 DLL 인터페이스의 일부로 간주 되지 않습니다. 따라서 해당 모듈 또는 같은 프로그램의 다른 모듈에 함수 또는 개체의 정의가 있어야 합니다. 함수 또는 개체를 DLL 인터페이스에 포함하려면 다른 모듈에서 함수 또는 개체의 정의를 `dllexport`로 선언해야 합니다. 그렇게 하지 않으면 링커 오류가 생성됩니다.  
  
     `dllexport` 특성을 사용하여 함수 또는 개체를 선언하면 해당 정의가 같은 프로그램의 일부 모듈에 나타나야 합니다. 그렇게 하지 않으면 링커 오류가 생성됩니다.  
  
-   프로그램의 모듈 하나에 둘 다 포함 하는 경우 **dllimport** 및 `dllexport` 같은 함수 또는 개체에 대 한 선언을 `dllexport` 특성 보다 우선는 **dllimport** 특성입니다. 그러나 이 경우 컴파일러 경고가 생성됩니다. 예를 들어:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   C + +에서 전역으로 선언 또는 정적 로컬 데이터 포인터를 초기화할 수 또는 사용 하 여 선언 된 데이터 개체의 주소와는 **dllimport** C에서 오류를 생성 하는 특성 또한으로 선언 된 함수의 주소로 정적 로컬 함수 포인터를 초기화할 수 있습니다는 **dllimport** 특성입니다. C에서는 이러한 대입으로 인해 포인터가 함수의 주소 대신 DLL 가져오기 썽크(함수로 제어를 전송하는 코드 스텁)의 주소로 설정됩니다. C++에서는 포인터가 함수의 주소로 설정됩니다. 예를 들어:  
  
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
  
     그러나 개체의 선언에 `dllexport` 특성을 포함하는 프로그램은 프로그램의 어딘가에 해당 개체의 정의를 제공해야 하므로 `dllexport` 함수의 주소로 전역 또는 로컬 정적 함수 포인터를 초기화할 수 있습니다. 마찬가지로 `dllexport` 데이터 개체의 주소로 전역 또는 로컬 정적 데이터 포인터를 초기화할 수 있습니다. 예를 들어, 다음 코드는 C 또는 C++에서 오류를 발생시키지 않습니다.  
  
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
  
-   적용 하는 경우 `dllexport` 에 표시 되지 않는 기본 클래스가 있는 일반 클래스에 `dllexport`, 컴파일러가 c 4275를 생성 합니다.  
  
     컴파일러는 기본 클래스가 클래스 템플릿의 특수화인 경우 동일한 경고를 생성합니다. 이 문제를 해결하려면 기본 클래스를 `dllexport`로 표시하십시오. 클래스 템플릿의 특수화의 문제점은 어디에 배치할지는 **__declspec (dllexport)**; 클래스 템플릿은 표시할 수 없습니다. 대신 명시적으로 클래스 템플릿을 인스턴스화하고 이 명시적 인스턴스화를 `dllexport`로 표시합니다. 예:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     템플릿 인수가 파생 클래스일 경우 이 해결 방법은 실패합니다. 예를 들어:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     이것은 템플릿의 공통 패턴이므로 하나 이상의 기본 클래스가 있는 클래스에 적용될 때 및 하나 이상의 기본 클래스가 클래스 템플릿의 특수화일 때 컴파일러가 `dllexport`의 의미 체계를 변경했습니다. 이 경우 컴파일러는 암시적으로 `dllexport`를 클래스 템플릿의 특수화에 적용합니다. 다음을 실행 및 경고를 가져올 수 있습니다.  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)