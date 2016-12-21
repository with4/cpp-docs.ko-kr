---
title: "스레드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "thread"
  - "thread_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], 스레드"
  - "thread __declspec 키워드"
  - "스레드 로컬 저장소(TLS)"
  - "TLS(스레드 로컬 저장소), 컴파일러 구현"
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 스레드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **thread** 확장 저장소 클래스 한정자는 스레드 지역 변수를 선언하는 데 사용됩니다.  C\+\+11의 이식 가능한 형식의 경우, [thread\_local](../cpp/storage-classes-cpp.md#thread_local) 저장소 클래스 지정자를 사용합니다.  
  
## 구문  
  
```  
  
__declspec( thread ) declarator  
```  
  
## 설명  
 TLS\(스레드 로컬 저장소\)는 다중 스레드 프로세스의 각 스레드가 스레드 데이터를 위한 저장소를 할당하는 메커니즘입니다.  표준 다중 스레드 프로그램에서 데이터는 지정된 프로세스의 모든 스레드에서 공유되지만 스레드 로컬 저장소는 스레드별 데이터를 할당하기 위한 메커니즘입니다.  스레드에 대한 자세한 내용은 [다중 스레딩](../parallel/multithreading-support-for-older-code-visual-cpp.md)을 참조하세요.  
  
 스레드 지역 변수의 선언은 [확장된 특성 구문](../cpp/declspec.md)과 `__declspec`thread 키워드가 있는  **키워드를 사용해야 합니다.** 예를 들어, 다음 코드는 정수 스레드 지역 변수를 선언한 다음 값으로 초기화합니다.  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 스레드 지역 개체 및 변수를 선언하는 경우 다음과 같은 지침을 준수해야 합니다.  
  
-   데이터 선언 및 정의에 대해서만 **thread** 특성을 적용할 수 있습니다. **thread**는 함수 선언 또는 정의에 사용될 수 없습니다.  
  
-   **thread** 특성을 사용하면 DLL 가져오기의 [지연 로드](../build/reference/linker-support-for-delay-loaded-dlls.md)에 방해가 될 수 있습니다**.**  
  
-   XP 시스템에서는 DLL이 \_\_declspec\(thread\) 데이터를 사용하고 LoadLibrary를 통해 동적으로 로드되는 경우 `thread`가 올바르게 작동하지 않을 수 있습니다.  
  
-   정적 저장 기간이 있는 데이터 항목에만 **thread** 특성을 지정할 수 있습니다.  여기에는 전역 데이터 개체\(**static** 및 `extern`\), 지역 정적 개체 및 클래스의 정적 데이터 멤버가 포함됩니다.  자동 데이터 개체는 **thread** 특성을 사용하여 선언할 수 없습니다.  
  
-   스레드 로컬 개체의 선언과 정의가 같은 파일에서 발생하는지, 아니면 별도의 파일에서 발생하는지와 관계없이 해당 선언과 정의에 대해 **thread** 특성을 사용해야 합니다.  
  
-   **thread** 특성은 형식 한정자로 사용할 수 없습니다.  
  
-   **thread** 특성을 사용하는 개체를 선언할 수 있으므로 다음 두 예제는 의미 체계 면에서 같습니다.  
  
    ```  
    // declspec_thread_2.cpp  
    // compile with: /LD  
    __declspec( thread ) class B {  
    public:  
       int data;  
    } BObject;   // BObject declared thread local.  
  
    class B2 {  
    public:  
       int data;  
    };  
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.  
    ```  
  
-   표준 C에서는 비정적 범위의 개체에 한해 자신에 대한 참조를 포함하는 식으로 개체 또는 변수를 초기화할 수 있습니다.  C\+\+에서는 일반적으로 자신에 대한 참조를 포함하는 식으로 개체를 동적으로 초기화할 수 있지만 스레드 로컬 개체에 대해서는 이렇게 초기화할 수 없습니다.  예:  
  
    ```  
    // declspec_thread_3.cpp  
    // compile with: /LD  
    #define Thread __declspec( thread )  
    int j = j;   // Okay in C++; C error  
    Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
    ```  
  
     초기화되는 개체를 포함하는 `sizeof` 식은 자신에 대한 참조로 간주되지 않으므로 C와 C\+\+에서 허용됩니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [TLS](../parallel/thread-local-storage-tls.md)