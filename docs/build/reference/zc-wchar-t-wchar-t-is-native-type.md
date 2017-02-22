---
title: "/Zc:wchar_t(wchar_t를 네이티브 형식으로 인식) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType"
  - "VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType"
  - "/Zc:wchar_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션[C++]"
  - "규칙 컴파일러 옵션"
  - "wchar_t 형식"
  - "Zc 컴파일러 옵션[C++]"
  - "-Zc 컴파일러 옵션[C++]"
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# /Zc:wchar_t(wchar_t를 네이티브 형식으로 인식)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ 표준에 따라 `wchar_t`를 기본 제공 형식으로 구문 분석합니다.  **\/Zc:wchar\_t**는 기본적으로 사용하도록 설정되어 있습니다.  
  
## 구문  
  
```  
/Zc:wchar_t[-]  
```  
  
## 설명  
 **\/Zc:wchar\_t**가 사용하도록 설정되어 있으면 `wchar_t`는 Microsoft 전용 네이티브 형식 `__wchar_t`에 매핑됩니다.  빼기 부호가 붙은 **\/Zc:wchar\_t\-**가 지정되었으면 `wchar_t`는 `unsigned short`에 대한 `typedef`에 매핑됩니다.  \(Visual C\+\+ 6.0 및 이전 버전에서는 `wchar_t`가 기본 제공 형식으로 구현되지 않았지만 wchar.h에서 `unsigned short`에 대한 `typedef`로 선언되었습니다.\) C\+\+ 표준에서는 `wchar_t`가 기본 제공 형식이어야 하기 때문에 **\/Zc:wchar\_t\-**를 사용하지 않는 것이 좋습니다.  `typedef` 버전을 사용하면 이식성 문제가 발생할 수 있습니다.  이전 버전의 Visual C\+\+에서 업그레이드하고 코드가 `wchar_t`를 `unsigned short`로 암시적으로 변환하려 하기 때문에 컴파일러 오류 [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)가 발생하는 경우 **\/Zc:wchar\_t\-**를 설정하는 대신 오류를 수정하기 위해 코드를 변경하는 것이 좋습니다.  
  
 Microsoft는 `wchar_t`를 2바이트 부호 없는 값으로 구현합니다.  `wchar_t`에 대한 자세한 내용은 [데이터 형식 범위](../../cpp/data-type-ranges.md) 및 [기본 형식](../../cpp/fundamental-types-cpp.md)을 참조하십시오.  
  
 `typedef` 버전의 `wchar_t`를 그대로 사용하는 이전 코드와 상호 운용해야 하는 새 코드를 작성하는 경우 코드를 **\/Zc:wchar\_t**로 컴파일된 코드 또는 그것으로 컴파일되지 않은 코드에 연결할 수 있도록 `wchar_t`의 `unsigned short` 및 `__wchar_t` 변형 모두에 대한 오버로드를 제공할 수 있습니다.  그렇지 않으면 서로 다른 두 빌드의 라이브러리\(**\/Zc:wchar\_t**가 사용하도록 설정된 라이브러리와 사용하지 않도록 설정된 라이브러리\)를 제공해야 합니다.  그러나 이 경우 새 코드를 컴파일하는 데 사용하는 것과 같은 컴파일러를 사용하여 이전 코드를 빌드하는 것이 좋습니다.  다른 컴파일러로 컴파일된 이진 파일을 혼합해서는 안 됩니다.  
  
 **\/Zc:wchar\_t**가 지정된 경우 **\_WCHAR\_T\_DEFINED** 및 **\_NATIVE\_WCHAR\_T\_DEFINED** 기호가 정의됩니다.  자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)을 참조하십시오.  
  
 코드가 컴파일러 COM 전역 함수를 사용하는 경우 이제 **\/Zc:wchar\_t**가 기본적으로 설정되기 때문에 명시적 참조를 [comment pragma](../../preprocessor/comment-c-cpp.md)에서 comsupp.lib로 변경하거나 명령줄에서는 comsuppw.lib 또는 comsuppwd.lib로 변경하는 것이 좋습니다.  **\/Zc:wchar\_t\-**를 사용해서 컴파일해야 하는 경우 comsupp.lib를 사용합니다. comdef.h 헤더 파일을 포함한 경우 올바른 라이브러리가 지정됩니다.  컴파일러 COM 지원에 대한 자세한 내용은 [컴파일러 COM 지원](../../cpp/compiler-com-support.md)를 참조하십시오.  
  
 컴파일 C 코드를 사용하는 경우 `wchar_t` 형식은 지원되지 않습니다.  Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  왼쪽 창에서 **구성 속성**, **C\/C\+\+**를 확장한 후 **언어**를 선택합니다.  
  
3.  **wchar\_t를 기본 제공 형식으로 처리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>을 참조하십시오.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)