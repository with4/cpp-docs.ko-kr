---
title: "#import 지시문 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#import"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import 지시문"
  - ".tlh 파일"
  - "COM, 형식 라이브러리 헤더 파일"
  - "Import 지시문(#import)"
  - "전처리기, 지시문"
  - "tlbid 스위치"
  - "tlh 파일"
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #import 지시문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 형식 라이브러리의 정보를 통합하는 데 사용됩니다.  형식 라이브러리의 콘텐츠는 대부분 COM 인터페이스를 설명하는 C\+\+ 클래스로 변환됩니다.  
  
## 구문  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
#### 매개 변수  
 *filename*  
 가져올 형식 라이브러리를 지정합니다.  `filename`은 다음 중 하나일 수 있습니다.  
  
-   .olb, .tlb 또는 .dll 파일 등 형식 라이브러리를 포함하는 파일 이름입니다.  **file:** 키워드는 각 파일 이름 앞에 올 수 있습니다.  
  
-   형식 라이브러리에서 제어의 progid입니다.  **progid:** 키워드는 각 progid 앞에 올 수 있습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     ProgID에 대한 자세한 내용은 [지역화 ID 및 버전 번호 지정](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)을 참조하십시오.  
  
     64비트 운영 체제에서 크로스 컴파일러를 사용하여 컴파일할 때 컴파일러는 32비트 레지스트리 하이브만 읽을 수 있습니다.  64비트 형식 라이브러리를 빌드 및 등록하기 위해 네이티브 64비트 컴파일러를 사용할 수도 있습니다.  
  
-   형식 라이브러리의 라이브러리 ID입니다.  **libid:** 키워드는 각 라이브러리 ID 앞에 올 수 있습니다.  예를 들면 다음과 같습니다.  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     버전 또는 lcid를 지정하지 않는 경우 **progid:**에 적용되는 [규칙](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)이 **libid:**에도 적용됩니다.  
  
-   실행 파일\(.exe\)입니다.  
  
-   .ocx와 같은 형식 라이브러리 리소스를 포함하는 라이브러리 파일\(.dll\)입니다.  
  
-   형식 라이브러리를 보유하는 복합 문서입니다.  
  
-   **LoadTypeLib** API가 인식할 수 있는 다른 임의의 파일 형식입니다.  
  
 `attributes`  
 하나 이상의 [\#import 특성](#_predir_the_23import_directive_import_attributes)입니다.  공백이나 쉼표를 사용하여 특성을 구분합니다.  예를 들면 다음과 같습니다.  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
 또는  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## 설명  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a> 파일 이름의 검색 순서  
 *filename*은 선택적으로 디렉터리 사양 뒤에 옵니다.  이 파일 이름은 기존 파일의 이름이어야 합니다.  두 구문 형식의 차이는 경로가 불완전하게 지정되어 있을 경우 전처리기가 형식 라이브러리 파일을 검색하는 순서입니다.  
  
|구문 형식|작업|  
|-----------|--------|  
|따옴표로 묶인 형식|전처리기가 우선 `#import` 문을 포함하는 파일의 디렉터리에서 형식 라이브러리 파일을 검색한 다음, 해당 파일을 포함하는\(`#include`\) 모든 파일의 디렉터리를 검색하도록 지시합니다.  그런 다음 전처리기는 아래 표시된 경로를 따라 검색합니다.|  
|꺾쇠 괄호 형식|전처리기가 다음 경로에 따라 형식 라이브러리 파일을 검색하도록 지시합니다.<br /><br /> 1.  **PATH** 환경 변수 경로 목록<br />2.  **LIB** 환경 변수 경로 목록<br />3.  \/I\(추가 포함 디렉터리\) 컴파일러 옵션에 의해 지정되는 경로 \- 이 경로를 제외하고 컴파일러에서 [no\_registry](../preprocessor/no-registry.md) 특성의 다른 형식 라이브러리에서 참조된 형식 라이브러리를 검색합니다.|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> 지역화 ID 및 버전 번호 지정  
 progid를 지정할 때 progid의 지역화 ID 및 버전 번호를 지정할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
 지역화 ID를 지정하지 않는 경우 progid는 다음 규칙에 따라 선택됩니다.  
  
-   지역화 ID가 하나만 있는 경우 해당 ID가 사용됩니다.  
  
-   지역화 ID가 둘 이상인 경우 버전 번호가 0, 9 또는 409인 첫 번째 ID가 사용됩니다.  
  
-   지역화 ID가 둘 이상이고 그 중 아무 것도 0, 9 또는 409가 아닌 경우 마지막 ID가 사용됩니다.  
  
-   버전 번호를 지정하지 않는 경우 최신 버전이 사용됩니다.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> 가져오기로 만든 헤더 파일  
 `#import`는 C\+\+ 소스 코드에서 형식 라이브러리 콘텐츠를 다시 생성하는 두 가지 헤더 파일을 만듭니다.  기본 헤더 파일은 MIDL\(Microsoft Interface Definition Language\) 컴파일러에 의해 생성된 파일과 비슷하지만 컴파일러에서 생성된 코드와 데이터를 파일 내에 추가합니다.  [기본 헤더 파일](#_predir_the_primary_type_library_header_file)은 형식 라이브러리와 같은 기본 이름과 .TLH 확장명을 가집니다.  보조 헤더 파일은 .TLI 확장명을 가진 형식 라이브러리와 같은 기본 이름을 가집니다.  이 파일은 컴파일러에서 생성된 멤버 함수에 대한 구현을 포함하고 기본 헤더 파일에 포함\(`#include`\)되어 있습니다.  
  
 byref 매개 변수를 사용하는 dispinterface 속성을 가져올 경우 \#import는 함수에 대한 \_\_declspec\([속성](../cpp/property-cpp.md)\) 문을 생성하지 않습니다.  
  
 두 헤더 파일이 모두 \/Fo\(이름 개체 파일\) 옵션에 의해 지정된 출력 디렉터리에 배치됩니다.  그런 다음 이러한 파일은 마치 기본 헤더 파일이 `#include` 지시문에 의해 명명된 것처럼 컴파일러에 의해 읽혀지고 컴파일됩니다.  
  
 다음과 같은 컴파일러 최적화는 `#import` 지시문에 있습니다.  
  
-   헤더 파일은 만들어질 때 형식 라이브러리와 동일한 타임스탬프를 제공받습니다.  
  
-   `#import`가 처리될 때 컴파일러는 먼저 헤더가 존재하며 최신 상태인지 확인합니다.  그렇다면 다시 만들 필요가 없습니다.  
  
 `#import` 지시문도 최소 다시 빌드에 참여하고 미리 컴파일된 헤더 파일에 배치될 수 있습니다.  자세한 내용은 [미리 컴파일된 헤더 파일 만들기](../build/reference/creating-precompiled-header-files.md)를 참조하십시오.  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> 기본 형식 라이브러리 헤더 파일  
 기본 형식 라이브러리 헤더 파일은 다음과 같은 7개의 섹션으로 구성됩니다.  
  
-   제목 상용구: 주석, COMDEF.H용 `#include` 문\(헤더에 사용되는 일부 표준 매크로 정의\) 및 다른 기타 설정 정보로 구성됩니다.  
  
-   정방향 참조 및 typedef: `struct IMyInterface` 및 typedef와 같은 구조체 선언으로 구성됩니다.  
  
-   스마트 포인터 선언: 템플릿 클래스 `_com_ptr_t`는 인터페이스 포인터를 캡슐화하고 `AddRef`, **Release** 및 `QueryInterface` 함수를 호출할 필요가 없도록 하는 스마트 포인터 구현입니다.  또한 새 COM 개체를 만들 경우 `CoCreateInstance` 호출을 숨깁니다.  이 섹션에서는 [\_com\_ptr\_t](../cpp/com-ptr-t-class.md) 템플릿 클래스의 템플릿 특수화가 될 COM 인터페이스의 typedef를 설정하기 위해 매크로 문 **\_COM\_SMARTPTR\_TYPEDEF**를 사용합니다.  예를 들어 **IMyInterface** 인터페이스의 경우 .TLH 파일에 다음이 포함됩니다.  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     컴파일러는 다음과 같이 확장됩니다.  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     `IMyInterfacePtr` 형식은 원시 인터페이스 포인터 `IMyInterface*` 대신 사용할 수 있습니다.  따라서 다양한 **IUnknown** 멤버 함수를 호출할 필요가 없습니다.  
  
-   Typeinfo 선언: 주로 클래스 정의와 **ITypeLib:GetTypeInfo**에 의해 반환되는 개별 typeinfo 항목을 노출시키는 기타 항목으로 구성됩니다.  이 섹션에서 형식 라이브러리의 각 typeinfo는 `TYPEKIND` 정보에 종속적인 형식의 헤더에 반영됩니다.  
  
-   선택적 기존 형식 GUID 정의: 명명된 GUID 상수의 초기화를 포함합니다.  이들은 **CLSID\_CoClass** 및 **IID\_Interface** 형식의 이름으로, MIDL 컴파일러에서 생성한 것과 비슷합니다.  
  
-   보조 형식 라이브러리 헤더에 대한 `#include` 문입니다.  
  
-   바닥글 상용구: 현재 `#pragma pack(pop)`을 포함합니다.  
  
 제목 상용구과 바닥글 상용구 섹션을 제외한 모든 섹션은 원본 IDL 파일에 있는 **library** 문으로 지정된 이름을 사용하는 네임스페이스로 둘러싸입니다.  네임스페이스 이름으로 명시적으로 한정하거나 다음 문을 포함하여 형식 라이브러리 헤더의 이름을 사용할 수 있습니다.  
  
```  
using namespace MyLib;  
```  
  
 소스 코드의 `#import` 문 직후  
  
 `#import` 지시문의 [no\_namespace](#_predir_no_namespace) 특성을 사용하여 네임스페이스를 표시하지 않을 수 있습니다.  하지만 네임스페이스를 표시하지 않으면 이름이 충돌될 수 있습니다.  [rename\_namespace](#_predir_rename_namespace) 특성에서 네임스페이스 이름을 변경할 수도 있습니다.  
  
 컴파일러는 현재 처리하고 있는 형식 라이브러리에 필요한 임의의 형식 라이브러리 종속성에 대한 전체 경로를 제공합니다.  경로는 컴파일러가 처리된 각 형식 라이브러리에 대해 생성하는 형식 라이브러리 헤더\(.TLH\)에 주석 형식으로 기록됩니다.  
  
 형식 라이브러리에 다른 형식 라이브러리에 정의된 형식에 대한 참조가 포함된 경우 .TLH 파일에 다음과 같은 유형의 주석이 포함됩니다.  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
 `#import` 주석의 실제 파일 이름은 레지스트리에 저장된 대로 상호 참조 형식 라이브러리의 전체 경로입니다.  형식 정의가 없어 오류가 발생하는 경우 .TLH 헤드의 주석을 확인하여 가장 먼저 가져와야 할 종속 형식 라이브러리를 확인하십시오.  .TLI 파일을 컴파일하는 동안 발생 가능성이 높은 오류는 구문 오류\(예: C2143, C2146, C2321\), C2501\(decl\-specifiers 누락\) 또는 C2433\(데이터 선언에 '인라인'이 허용되지 않음\)입니다.  
  
 오류를 해결하려면 종속성 주석이 시스템 헤더에 의해 제공되지 않는 형식 라이브러리를 확인한 다음 종속 형식 라이브러리의 `#import` 지시문 앞에 있는 일부 지점에 `#import` 지시문을 제공해야 합니다.  
  
 자세한 내용은 기술 자료 문서인 "\#import Wrapper Methods May Cause Access Violation"\(Q242527\) 또는 "Compiler Errors When You Use \#import with XML"\(Q269194\)를 참조하십시오.  기술 자료 문서는 MSDN 라이브러리 미디어 또는 [http:\/\/support.microsoft.com\/support\/](http://support.microsoft.com/support/)에 있습니다.  
  
##  <a name="_predir_the_23import_directive_import_attributes"></a> \#import 특성  
 `#import`는 하나 이상의 특성을 선택적으로 포함할 수 있습니다.  이러한 특성은 컴파일러가 형식 라이브러리 헤더의 콘텐츠를 수정하도록 지시합니다.  백슬래시\(**\\**\) 기호를 사용하여 단일 `#import` 문에 추가 줄을 포함할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
 자세한 내용은 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)을 참조하십시오.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)   
 [컴파일러 COM 지원](../cpp/compiler-com-support.md)