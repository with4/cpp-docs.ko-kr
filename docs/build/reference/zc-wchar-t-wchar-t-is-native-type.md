---
title: '-Zc: wchar_t (wchar_t Is Native Type) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3375e39120fdc8f2b0d8d5502aa6def997511ff5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t(wchar_t를 네이티브 형식으로 인식)
C++ 표준에 따라 `wchar_t`를 기본 제공 형식으로 구문 분석합니다. 기본적으로 **/zc: wchar_t** 켜져 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Zc:wchar_t[-]  
```  
  
## <a name="remarks"></a>설명  
 경우 **/zc: wchar_t** 켜져 `wchar_t` Microsoft 전용 네이티브 형식으로 매핑됩니다 `__wchar_t`합니다. 경우 **/Zc:wchar_t-** (빼기 기호)로 지정 `wchar_t` 매핑되는 `typedef` 에 대 한 `unsigned short`합니다. (Visual C++ 6.0 및 이전 버전에서는 `wchar_t`가 기본 제공 형식으로 구현되지 않았지만 wchar.h에서 `typedef`에 대한 `unsigned short`로 선언되었습니다.) 권장 하지는 않습니다 **/Zc:wchar_t-** 하는 c + + 표준 필요 하기 때문에 `wchar_t` 기본 제공 형식 이어야 합니다. `typedef` 버전을 사용하면 이식성 문제가 발생할 수 있습니다. 이전 버전의 Visual c + +에서 업그레이드 하 고 컴파일러 오류가 발생할 경우 [c 2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) 암시적으로 변환 하려고 하기 때문에 `wchar_t` 를 `unsigned short`, 대신 오류를 해결 하는 코드를 변경 하는 것이 좋습니다 설정의 **/Zc:wchar_t-**합니다.  
  
 Microsoft는 `wchar_t`를 2바이트 부호 없는 값으로 구현합니다. 에 대 한 자세한 내용은 `wchar_t`, 참조 [데이터 형식 범위](../../cpp/data-type-ranges.md) 및 [기본 형식을](../../cpp/fundamental-types-cpp.md)합니다.  
  
 계속 사용 하는 이전 코드와 상호 운용 하는 새 코드를 작성 하는 경우는 `typedef` 버전의 `wchar_t`, 둘 다에 대해 오버 로드를 제공할 수 있습니다는 `unsigned short` 및 `__wchar_t` 형태의 링크 만들기 `wchar_t`코드와 연결 될 수 있도록, 로 컴파일된 코드 **/zc: wchar_t** 또는 그것으로 컴파일되지 않은 코드입니다. 다른 두 빌드의 라이브러리를 제공 해야 하는 그렇지 않은 경우-한 없이 **/zc: wchar_t** 사용 하도록 설정 합니다. 그러나 이 경우 새 코드를 컴파일하는 데 사용하는 것과 같은 컴파일러를 사용하여 이전 코드를 빌드하는 것이 좋습니다. 다른 컴파일러로 컴파일된 이진 파일을 혼합해서는 안 됩니다.  
  
 때 **/zc: wchar_t** 지정 된 **_WCHAR_T_DEFINED** 및 **_NATIVE_WCHAR_T_DEFINED** 기호를 정의 합니다. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오.  
  
 코드 때문에 컴파일러 COM 전역 함수를 사용 하는 경우 **/zc: wchar_t** 기본적으로 좋습니다 comsupp.lib로에 대 한 명시적 참조를 변경 하는 현재이 [주석 pragma](../../preprocessor/comment-c-cpp.md) 또는 명령에서 선-에서는 comsuppw.lib 또는 comsuppwd.lib를 합니다. (사용 하 여 컴파일하면 해야 **/Zc:wchar_t-**, comsupp.lib를 사용 합니다.) comdef.h 헤더 파일을 포함하는 경우 올바른 라이브러리가 지정됩니다. 컴파일러 COM 지원에 대 한 정보를 참조 하십시오. [컴파일러 COM 지원](../../cpp/compiler-com-support.md)합니다.  
  
 컴파일 C 코드를 사용하는 경우 `wchar_t` 형식은 지원되지 않습니다. Visual c + + 규칙과 관련 된 문제에 대 한 자세한 내용은 참조 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  왼쪽된 창에서 확장 **구성 속성**, **C/c + +**를 선택한 후 **언어**합니다.  
  
3.  수정 된 **wchar_t를 기본 제공 형식으로 처리** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/Zc (규칙)](../../build/reference/zc-conformance.md)