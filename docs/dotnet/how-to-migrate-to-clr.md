---
title: "방법: /clr로 마이그레이션 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 컴파일러 옵션[C++], 포팅"
  - "네이티브 코드 컴파일[C++]"
  - "interop[C++], /clr 컴파일러 옵션"
  - "상호 운용성[C++], /clr 컴파일러 옵션"
  - "마이그레이션[C++], /clr 컴파일러 옵션"
  - "Visual C++ 응용 프로그램 업그레이드, /clr 컴파일러 옵션"
ms.assetid: c9290b8b-436a-4510-8b56-eae51f4a9afc
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# 방법: /clr로 마이그레이션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 네이티브 코드 **\/clr**를 사용하여 컴파일할 때 발생하는 문제에 대해 설명합니다\(자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md) 참조\).  **\/clr**를 사용하면 Visual C\+\+ 모듈이 관리되지 않는 모듈과의 호환성을 유지하면서 .NET 어셈블리를 호출하고 호출을 받을 수 있습니다.  **\/clr**로 컴파일할 때의 장점에 대한 자세한 내용은 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md) 및 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)을 참조하십시오.  
  
## 라이브러리 프로젝트를 \/clr로 컴파일할 때 발생하는 알려진 문제점  
 Visual Studio에서 라이브러리 프로젝트를 **\/clr**로 컴파일할 때 발생하는 몇 가지 문제점이 알려져 있습니다.  
  
-   코드에서는 런타임에 [CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md)을 사용하여 형식을 쿼리할 수 있습니다.  그러나 형식이 **\/clr**로 컴파일된 MSIL .dll인 경우 관리되는 .dll에서 정적 생성자가 실행되기 전에 [CRuntimeClass::FromName](../Topic/CRuntimeClass::FromName.md)을 호출하면 호출에 실패합니다. 관리되는 .dll에서 코드가 실행된 후에 FromName을 호출하면 이 문제가 발생하지 않습니다.  이 문제를 해결하려면 관리되는 .dll에 함수를 정의하고 내보낸 다음 네이티브 MFC 응용 프로그램에서 이 함수를 호출하는 방법으로 관리되는 정적 생성자를 구성해야 합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    // Extension DLL Header file:  
    __declspec( dllexport ) void EnsureManagedInitialization () {  
       // managed code that won't be optimized away  
       System::GC::KeepAlive(System::Int32::MaxValue);  
    }  
    ```  
  
## Visual C\+\+에서 컴파일  
 프로젝트의 모듈에 **\/clr**를 사용하기 전에 우선 네이티브 프로젝트를 Visual Studio 2010에서 컴파일하고 링크하십시오.  
  
 다음 단계를 순서대로 수행하면 가장 간편하게 **\/clr** 컴파일을 수행할 수 있습니다.  이러한 각 단계를 마친 후 프로젝트를 컴파일하고 실행해야 합니다.  
  
### Visual C\+\+ 2003 이전 버전  
 Visual C\+\+ 2003 이전 버전에서 Visual Studio 2010으로 업그레이드하는 경우 Visual C\+\+ 2003의 강화된 C\+\+ 표준 호환성과 관련된 컴파일러 오류가 발생할 수 있습니다.  
  
### Visual C\+\+ 2003에서 업그레이드  
 Visual Studio의 강화된 ANSI\/ISO 규격 준수 및 주요 변경 사항으로 인해 이전에 Visual C\+\+ 2003에서 빌드한 프로젝트는 우선 **\/clr**를 사용하지 않고 컴파일해야 합니다.  가장 주의 깊게 살펴 보아야 할 변경 내용은 [CRT의 보안 기능](../c-runtime-library/security-features-in-the-crt.md)입니다.  CRT를 사용하는 코드에서는 더 이상 사용되지 않는다는 경고가 발생할 가능성이 큽니다.  이러한 경고를 억제할 수도 있지만, 향상된 보안을 제공하고 코드에서 보안 문제를 발견할 수 있는 새로운 [보안이 강화된 CRT 함수 버전](../c-runtime-library/security-enhanced-versions-of-crt-functions.md)로 마이그레이션하는 것이 좋습니다.  
  
### Managed Extensions for C\+\+에서 업그레이드  
 Managed Extensions for C\+\+를 사용하는 Visual C\+\+ .NET 또는 Visual C\+\+ 2003에서 빌드한 프로젝트에서는 이들 확장이 더 이상 사용되지 않으므로 프로젝트 설정에서 적어도 하나의 항목을 변경해야 합니다.  따라서 Managed Extentions for C\+\+로 작성된 코드는 **\/clr**로 컴파일할 수 없습니다.  대신 **\/clr:oldSyntax**를 사용하십시오.  
  
## C 코드를 C\+\+로 변환  
 Visual Studio에서는 C 파일을 컴파일하지만 **\/clr** 컴파일의 경우 C\+\+로 변환해야 합니다.  실제 파일 이름을 변경할 필요는 없으며, **\/Tp**\([\/Tc, \/Tp, \/TC, \/TP\(소스 파일 형식 지정\)](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 참조\)를 사용할 수 있습니다. **\/clr**에는 C\+\+ 소스 코드 파일이 필요하지만, 개체 지향 패러다임을 사용하도록 코드를 리팩터링할 필요는 없습니다.  
  
 C 코드를 C\+\+ 파일로 컴파일하려면 코드를 변경해야 할 가능성이 큽니다.  C\+\+ 형식이 안전한 규칙은 매우 엄격하므로 캐스트를 사용하여 명시적으로 형식 변환을 수행해야 합니다.  예를 들어 malloc은 void 포인터를 반환하지만 캐스트를 사용하여 C에서 모든 형식의 포인터에 할당할 수 있습니다.  
  
```  
int* a = malloc(sizeof(int));   // C code  
int* b = (int*)malloc(sizeof(int));   // C++ equivalent  
```  
  
 C\+\+의 함수 포인터도 엄격하게 형식이 안전하므로 다음과 같은 C 코드는 수정되어야 합니다.  C\+\+에서는 함수 포인터 형식을 정의하는 `typedef`를 만든 다음 이 형식을 사용하여 함수 포인터를 캐스팅하는 것이 가장 좋습니다.  
  
```  
NewFunc1 = GetProcAddress( hLib, "Func1" );   // C code  
typedef int(*MYPROC)(int);   // C++ equivalent  
NewFunc2 = (MYPROC)GetProcAddress( hLib, "Func2" );  
```  
  
 또한 C\+\+에서는 함수를 참조하거나 호출하기 전에 프로토타입을 지정하거나 완전히 정의해야 합니다.  
  
 C 코드에 사용된 식별자가 C\+\+의 키워드\(`virtual`, `new`, `delete`, `bool`, `true`, `false` 등\)와 일치하는 경우 식별자의 이름을 변경해야 합니다.  일반적으로 이 작업은 간단한 검색 및 바꾸기 작업으로 수행할 수 있습니다.  
  
 마지막으로, C 스타일 COM 호출에서는 v\-table 및 `this` 포인터를 명시적으로 사용해야 하지만 C\+\+에서는 그렇지 않습니다.  
  
```  
COMObj1->lpVtbl->Method(COMObj, args);  // C code  
COMObj2->Method(args);  // C++ equivalent  
```  
  
## 프로젝트 설정 다시 구성  
 프로젝트를 컴파일하고 Visual Studio 2010에서 실행한 후에 기본 구성을 수정하는 대신 **\/clr**에 대해 새 프로젝트 구성을 만들어야 합니다.  **\/clr**는 일부 컴파일러 옵션에는 호환되지 않으며 별도의 구성을 만들면 네이티브 또는 관리되는 프로젝트를 만들 수 있습니다.  속성 페이지 대화 상자에서 **\/clr**를 선택하면 **\/clr**와 호환되지 않는 프로젝트 설정이 비활성화되며, 비활성화된 옵션은 이후에 **\/clr**의 선택을 해제해도 자동으로 복원되지 않습니다.  
  
### 새 프로젝트 구성 만들기  
 [New Project Configuration Dialog Box](http://msdn.microsoft.com/ko-kr/cca616dc-05a6-4fe3-bdc1-40c72a66f2be)의 **다음에서 설정 복사** 옵션을 사용하여 기존 프로젝트 설정을 기반으로 프로젝트 구성을 만들 수 있습니다.  디버그 구성과 릴리스 구성에 대해 이를 한 번씩 수행합니다.  그런 다음 원래 프로젝트 구성은 수정하지 않고 **\/clr** 관련 구성만 변경할 수 있습니다.  
  
 사용자 지정 빌드 규칙을 사용하는 프로젝트에는 추가로 주의를 기울여야 합니다.  
  
 이 단계는 메이크파일을 사용하는 프로젝트에는 다르게 적용됩니다.  이러한 경우에는 별도의 빌드 대상을 구성하거나, 원본의 복사본에서 **\/clr** 컴파일 전용 버전을 만들 수 있습니다.  
  
### 프로젝트 설정 변경  
 [\/clr\(공용 언어 런타임 컴파일\)](../build/reference/clr-common-language-runtime-compilation.md)의 설명에 따라 개발 환경에서 **\/clr**를 선택할 수 있습니다.  앞에서 설명한 것처럼 이 단계를 수행하면 충돌하는 프로젝트 설정이 자동으로 비활성화됩니다.  
  
> [!NOTE]
>  관리되는 라이브러리 또는 웹 서비스 프로젝트를 Visual C\+\+ 2003에서 업그레이드하면 **명령줄** 속성 페이지에 **\/Zl** 컴파일러 옵션이 추가됩니다.  이로 인해 LNK2001이 발생합니다.  이 문제를 해결하려면 **명령줄** 속성 페이지에서 **\/Zl**를 제거합니다.  자세한 내용은 [\/Zl\(기본 라이브러리 이름 생략\)](../build/reference/zl-omit-default-library-name.md) 및 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)을 참조하십시오.  또는 링커의 **추가 종속성** 속성에 msvcrt.lib와 msvcmrt.lib를 추가하십시오.  
  
 메이크파일로 빌드된 프로젝트의 경우 **\/clr**가 추가되면 호환되지 않는 컴파일러 옵션을 직접 비활성화해야 합니다.  **\/clr**와 호환되지 않는 컴파일러 옵션에 대한 자세한 내용은 [\/clr 제한](../build/reference/clr-restrictions.md)을 참조하십시오.  
  
### 미리 컴파일된 헤더  
 미리 컴파일된 헤더는 **\/clr**에서 지원됩니다.  그러나 CPP 파일 중 일부만 **\/clr**로 컴파일하고 나머지 파일을 네이티브로 컴파일하는 경우, **\/clr**로 생성된 미리 컴파일된 헤더가 **\/clr**를 사용하지 않고 생성된 헤더와 호환되지 않으므로 일부 변경이 필요합니다.  이러한 비호환성이 발생하는 이유는 **\/clr**에서 메타데이터를 생성하고 요구하기 때문입니다.  따라서 **\/clr**로 컴파일된 모듈에서는 메타데이터를 포함하지 않는 미리 컴파일된 헤더를 사용할 수 없고, **\/clr**가 아닌 모듈에서는 메타데이터를 포함하는 미리 컴파일된 헤더를 사용할 수 없습니다.  
  
 일부 모듈이 **\/clr**로 컴파일되는 프로젝트를 컴파일하는 가장 쉬운 방법은 미리 컴파일된 헤더를 모두 해제하는 것입니다. 프로젝트 속성 페이지 대화 상자에서 C\/C\+\+ 노드를 열고 미리 컴파일된 헤더를 선택합니다.  그런 다음 미리 컴파일된 헤더 만들기\/사용 속성을 "미리 컴파일된 헤더 사용 안 함"으로 변경합니다.  
  
 그러나 특히 대규모 프로젝트에서는 미리 컴파일된 헤더를 사용하면 컴파일 속도가 대폭 향상되므로 이 기능을 해제하지 않는 것이 좋습니다.  이러한 경우에는 **\/clr** 파일과 **\/clr**가 아닌 파일에서 별도의 미리 컴파일된 헤더를 사용하도록 구성하는 것이 가장 좋습니다.  이 작업을 한 단계로 수행하려면 **\/clr**로 컴파일할 여러 모듈을 솔루션 탐색기에서 선택하고 이 그룹을 마우스 오른쪽 단추로 클릭한 다음 속성을 선택합니다.  그런 다음 파일에서 PCH 만들기\/사용 속성과 미리 컴파일된 헤더 파일 속성을 각각 다른 PCH 파일과 헤더 파일을 사용하도록 변경합니다.  
  
## 오류 수정  
 **\/clr**를 사용하여 컴파일할 때 컴파일러 오류, 링커 오류 또는 런타임 오류가 발생할 수 있습니다.  이 단원에서는 가장 일반적인 문제에 대해 설명합니다.  
  
### 메타데이터 병합  
 데이터 형식의 버전이 다른 경우 두 형식에 대해 생성된 메타데이터가 일치하지 않기 때문에 링커가 작업에 실패할 수 있습니다. 이 문제는 일반적으로 특정 형식의 멤버가 조건부로 정의되어 있지만 이 형식을 사용하는 CPP 파일 중 일부에서 조건이 다른 경우에 발생합니다. 이러한 경우 링커에서 작업에 실패하며, 기호 이름 및 형식이 정의된 두 번째 OBJ 파일 이름만 보고됩니다.  링커에 전달되는 OBJ 파일의 순서를 바꾸면 데이터 형식의 다른 버전이 있는 위치를 쉽게 발견할 수 있습니다.  
  
### 로더 잠금 교착 상태  
 Visual C\+\+ .NET 및 Visual C\+\+ 2003에서는 **\/clr**에서 초기화하면 명확하지 않은 교착 상태가 발생할 수 있었습니다.  이 문제는 "로더 잠금 교착 상태"라고 합니다.  Visual Studio 2010에서는 이 교착 상태를 피하기가 쉬워졌고, 런타임에 감지되고 보고되는 명확한 문제가 되었습니다.  로더 잠금 문제가 발생할 가능성은 여전히 남아 있지만 이 문제를 피하고 해결하기가 쉬워졌습니다.  자세한 배경, 지침 및 해결 방법은 [혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)를 참조하십시오.  
  
### 데이터 내보내기  
 DLL 데이터를 내보내는 것은 오류가 발생하기 쉬우며 권장되지 않습니다.  이는 DLL의 관리되는 부분 중 일부가 실행되기 전까지 DLL의 데이터 섹션이 초기화되지 않을 수 있기 때문입니다.  [\#using 지시문](../preprocessor/hash-using-directive-cpp.md)를 사용하여 메타데이터를 참조하십시오.  
  
### 형식 가시성  
 이제 네이티브 형식은 기본적으로 private입니다.  Visual C\+\+ .NET 2002와 Visual C\+\+ 2003에서는 네이티브 형식이 기본적으로 public입니다.  이로 인해 DLL 외부에서는 네이티브 형식을 볼 수 없습니다.  이 오류를 해결하려면 이러한 형식에 `public`을 추가합니다.  자세한 내용은 [형식 멤버 표시 유형](../misc/type-and-member-visibility.md)를 참조하십시오.  
  
### 부동 소수점 및 맞춤 문제  
 `__controlfp`는 공용 언어 런타임에서 지원되지 않습니다. 자세한 내용은 [\_control87, \_controlfp, \_\_control87\_2](../c-runtime-library/reference/control87-controlfp-control87-2.md)를 참조하십시오.  또한 CLR에서는 [맞춤](../cpp/align-cpp.md)을 처리하지 않습니다.  
  
### COM 초기화  
 공용 언어 런타임에서는 모듈이 초기화될 때 COM을 자동으로 초기화합니다. COM이 자동으로 초기화될 때 MTA도 마찬가지로 초기화됩니다.  따라서 COM을 명시적으로 초기화하면 COM이 이미 초기화되었음을 나타내는 반환 코드가 생성됩니다.  CLR에서 COM을 이미 특정 스레딩 모델로 초기화한 상태에서 COM을 다른 스레딩 모델로 명시적으로 초기화하려고 하면 응용 프로그램이 작동하지 않을 수 있습니다.  
  
 공용 언어 런타임에서는 기본적으로 COM을 MTA로 시작합니다. 이 동작을 수정하려면 [\/CLRTHREADATTRIBUTE\(CLR 스레드 특성 설정\)](../build/reference/clrthreadattribute-set-clr-thread-attribute.md)를 사용하십시오.  
  
### 성능 문제  
 MSIL로 생성된 네이티브 C\+\+ 메서드를 가상 함수 호출이나 함수 포인터를 사용하여 간접적으로 호출하면 성능이 저하될 수 있습니다.  여기에 대한 자세한 내용은 [이중 썽킹](../dotnet/double-thunking-cpp.md)을 참조하십시오.  
  
 네이티브에서 MSIL로 이동하면 작업 집합의 크기가 증가하는 것을 알 수 있습니다.  이는 공용 언어 런타임에서 프로그램이 제대로 실행되도록 하기 위한 여러 기능을 제공하기 때문입니다.  **\/clr** 응용 프로그램이 제대로 실행되지 않는 경우 기본적으로 해제되어 있는 C4793을 활성화하는 것이 좋습니다. 자세한 내용은 [컴파일러 경고\(수준 1 및 3\) C4793](../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md)을 참조하십시오.  
  
### 종료 시 프로그램 충돌  
 관리 코드의 실행이 끝나기 전에 CLR이 종료되는 경우가 있습니다.  `std::set_terminate` 및 `SIGTERM`을 사용하면 이러한 문제가 발생할 수 있습니다.  자세한 내용은 [신호 상수](../c-runtime-library/signal-constants.md) 및 [set\_terminate](../Topic/set_terminate%20\(%3Cexception%3E\).md)을 참조하십시오.  
  
## Visual C\+\+의 새로운 기능 사용  
 응용 프로그램을 컴파일하고, 링크하고, 실행한 후 **\/clr**로 컴파일된 모든 모듈에서 .NET 기능을 사용할 수 있습니다.  자세한 내용은 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)을 참조하십시오.  
  
 Managed Extensions for C\+\+를 사용한 경우 새 구문을 사용하도록 코드를 변환할 수 있습니다.  구문상 차이점에 대한 요약을 보려면 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ko-kr/edbded88-7ef3-4757-bd9d-b8f48ac2aada)을 참조하십시오.  Managed Extensions for C\+\+를 변환하는 데 대한 자세한 내용은 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)을 참조하십시오.  
  
 Visual C\+\+의 .NET 프로그래밍에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
  
-   [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)  
  
-   [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)  
  
## 참고 항목  
 [혼합형\(네이티브 및 관리\) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)