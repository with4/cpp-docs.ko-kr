---
title: "TLS | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "다중 스레딩[C++], 스레드 로컬 저장소"
  - "스레드별 데이터 저장"
  - "스레드 특성"
  - "스레드 로컬 저장소[C++]"
  - "스레딩[C++], 스레드 로컬 저장소"
  - "TLS[C++]"
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

TLS\(스레드 로컬 저장소\)는 지정된 다중 스레드 프로세스의 각 스레드에서 스레드별 데이터를 저장하는 위치를 할당하는 방법입니다.  동적으로 바인딩되는\(런타임\) 스레드별 데이터는 TLS API\([TlsAlloc](assetId:///TlsAlloc?qualifyHint=False&autoUpgrade=True), [TlsGetValue](assetId:///TlsGetValue?qualifyHint=False&autoUpgrade=True), [TlsSetValue](assetId:///TlsSetValue?qualifyHint=False&autoUpgrade=True) 및 [TlsFree](assetId:///TlsFree?qualifyHint=False&autoUpgrade=True)\)를 통해 지원됩니다.  Windows에서 스레드 로컬 저장소가 구현되는 방법에 대한 자세한 내용은 [스레드 로컬 저장소\(Windows\)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686749\(v=vs.85\).aspx)를 참조하세요.  Win32 및 Visual C\+\+ 컴파일러는 이제 기존 API 구현 외에도 정적으로 바인딩된\(로드 타임\) 스레드별 데이터도 지원합니다.  
  
##  <a name="_core_compiler_implementation_for_tls"></a> TLS의 컴파일러 구현  
 **C\+\+11:** `thread_local` 저장소 클래스 지정자는 클래스 멤버 및 개체에 대한 스레드 로컬 저장소를 지정하는 데 권장되는 방법입니다.  자세한 내용은 [저장소 클래스\(C\+\+\)](../../cpp/storage-classes-cpp.md#thread_local)를 참조하세요.  
  
 Visual C\+\+에서는 또한 Microsoft 전용 특성인 [스레드](../../cpp/thread.md)를 확장된 저장소 클래스 한정자로 제공합니다.  `__declspec` 키워드를 사용하여 **스레드** 변수를 선언합니다.  예를 들어, 다음 코드는 정수 스레드 지역 변수를 선언한 다음 값으로 초기화합니다.  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
## 규칙 및 제한 사항  
 정적으로 바인딩된 스레드 로컬 개체 및 변수를 선언할 때는 다음 지침을 준수해야 합니다.  다음 지침은 [스레드](../../cpp/thread.md)에 적용되며 상당 부분 [thread\_local](../../cpp/storage-classes-cpp.md#thread_local)에도 적용됩니다.  
  
-   `thread` 특성은 클래스 및 데이터 선언과 정의에만 적용할 수 있습니다.  함수 선언 또는 정의에는 사용할 수 없습니다.  예를 들어, 다음 코드는 컴파일러 오류를 생성합니다.  
  
    ```  
  
    __declspec( thread )void func();     // This will generate an error.  
    ```  
  
-   `thread` 한정자는 `static` 범위를 가진 데이터 항목에 대해서만 지정할 수 있습니다.  여기에는 전역 데이터 개체\(`static` 및 `extern`\), 지역 정적 개체 및 C\+\+ 클래스의 정적 데이터 멤버가 포함됩니다.  자동 데이터 개체는 `thread` 특성을 사용하여 선언할 수 없습니다.  다음 코드는 컴파일러 오류를 생성합니다.  
  
    ```  
  
    void func1()  
    {  
        __declspec( thread )int tls_i;            // This will generate an error.  
    }  
  
    int func2(__declspec( thread )int tls_i )    // This will generate an error.  
    {  
        return tls_i;  
    }  
    ```  
  
-   스레드 로컬 개체의 선언과 정의는 모두 `thread` 특성을 지정해야 합니다.  예를 들어, 다음 코드는 오류를 생성합니다.  
  
    ```  
    #define Thread  __declspec( thread )  
    extern int tls_i;        // This will generate an error, since the  
    int __declspec( thread )tls_i;        // declaration and definition differ.  
    ```  
  
-   `thread` 특성은 형식 한정자로 사용할 수 없습니다.  예를 들어, 다음 코드는 컴파일러 오류를 생성합니다.  
  
    ```  
    char __declspec( thread ) *ch;        // Error  
    ```  
  
-   `thread` 특성을 사용하는 C\+\+ 개체를 선언할 수 있으므로 다음 두 예제는 의미 체계 면에서 같습니다.  
  
    ```  
  
    __declspec( thread ) class B  
    {  
    // Code  
    } BObject;  // OK--BObject is declared thread local.  
  
    class B  
    {  
    // Code  
    };  
    __declspec( thread ) B BObject;  // OK--BObject is declared thread local.  
    ```  
  
-   스레드 로컬 개체의 주소는 상수로 간주되지 않으므로 이 주소를 포함하는 모든 식은 상수 식으로 간주되지 않습니다.  이는 표준 C의 경우 스레드 지역 변수의 주소를 개체나 포인터에 대한 이니셜라이저로 사용하지 못하게 하는 효과가 있습니다.  예를 들어 다음 코드는 C 컴파일러에서 오류로 플래그 지정됩니다.  
  
    ```  
  
    __declspec( thread )int tls_i;  
    int *p = &tls_i;       //This will generate an error in C.  
    ```  
  
     이 제한은 C\+\+에서는 적용되지 않습니다.  C\+\+에서는 모든 개체의 동적 초기화가 허용되기 때문에, 스레드 지역 변수의 주소를 사용하는 식을 사용하여 개체를 초기화할 수 있습니다.  이것은 마치 스레드 로컬 개체 생성과 같습니다.  예를 들어 앞에 나온 코드는 C\+\+ 소스 파일로 컴파일하면 오류를 생성하지 않습니다.  스레드 지역 변수의 주소는 이 주소가 사용된 스레드가 존재하는 동안에만 유효합니다.  
  
-   표준 C에서는 비정적 범위의 개체에 한해 자신에 대한 참조를 포함하는 식으로 개체 또는 변수를 초기화할 수 있습니다.  C\+\+에서는 일반적으로 자신에 대한 참조를 포함하는 식으로 개체를 동적으로 초기화할 수 있지만 스레드 로컬 개체에 대해서는 이런 종류의 초기화가 허용되지 않습니다.  예:  
  
    ```  
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++   
    int j = j;                               // OK in C++, error in C  
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++  
    ```  
  
     초기화되는 개체를 포함하는 `sizeof` 식은 자신에 대한 참조를 나타내지 않으므로 C와 C\+\+에서 모두 허용됩니다.  
  
     C\+\+에서는 향후 스레드 로컬 저장소 기능이 향상될 수 있으므로 이런 방식으로 스레드 데이터를 동적으로 초기화할 수 없습니다.  
  
-   [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 이전 Windows 운영 체제에서는 `__declspec`\( thread \)에 몇 가지 제한이 있습니다.  DLL에서 데이터 또는 개체를 `__declspec`\( thread \)로 선언하는 경우 동적으로 로드하면 보호 오류가 발생할 수 있습니다.  DLL에 [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)가 로드된 후에는 코드가 `__declspec`\( thread \) 데이터를 참조할 때마다 시스템 오류가 발생합니다.  런타임에 스레드에 대한 전역 변수 공간이 할당되기 때문에, 이 공간의 크기는 응용 프로그램의 요구 사항과 정적으로 연결되는 모든 DLL의 요구 사항을 계산하여 결정됩니다.  `LoadLibrary`를 사용할 때는 `__declspec`\( thread \)로 스레드 지역 변수를 선언할 수 있도록 이 공간을 확장할 수 없습니다.  DLL에 `LoadLibrary`가 로드될 수 있는 경우 DLL에서 [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801)와 같은 TLS API를 사용하여 TLS를 할당합니다.  
  
## 참고 항목  
 [C 및 Wind32를 사용한 다중 스레딩](../../parallel/multithreading-with-c-and-win32.md)   
 [TLS 규칙 및 제한](../../misc/rules-and-limitations-for-tls.md)