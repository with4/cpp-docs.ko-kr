---
title: "-MD-MT,-LD (런타임 라이브러리 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
dev_langs:
- C++
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b54a6aac55554cd7bd4698762779e540c4bc4c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD(런타임 라이브러리 사용)
다중 스레드 모듈이 DLL인지 나타내고 런타임 라이브러리의 정식 또는 디버그 버전을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/MD[d]  
/MT[d]  
/LD[d]  
```  
  
## <a name="remarks"></a>설명  
  
|옵션|설명|  
|------------|-----------------|  
|**/MD**|응용 프로그램에서 런타임 라이브러리의 다중 스레드별 및 DLL별 버전을 사용하게 됩니다. `_MT` 및 `_DLL`을 정의하고 컴파일러가 라이브러리 이름 MSVCRT.lib를 .obj 파일에 배치하게 만듭니다.<br /><br /> 이 옵션을 사용하여 컴파일한 응용 프로그램은 MSVCRT.lib에 정적으로 연결됩니다. 이 라이브러리는 링커가 외부 참조를 확인할 수 있는 코드의 계층을 제공합니다. 실제 작업 코드 MSVCR에 포함 된*versionnumber*합니다. DLL MSVCRT.lib에 연결 하는 응용 프로그램 실행 시 사용할 수 있어야 합니다.|  
|**/MDd**|`_DEBUG`, `_MT` 및 `_DLL`을 정의하고 응용 프로그램에서 런타임 라이브러리의 디버그 다중 스레드 DLL별 버전을 사용하게 됩니다. 또한 컴파일러가 라이브러리 이름 MSVCRTD.lib를 .obj 파일에 배치하게 만듭니다.|  
|**/MT**|응용 프로그램에서 런타임 라이브러리의 다중 스레드 정적 버전을 사용하게 됩니다. `_MT`를 정의하며, 링커가 LIBCMT.lib를 사용하여 외부 기호를 확인하도록 컴파일러가 라이브러리 이름인 LIBCMT.lib를 .obj 파일에 추가합니다.|  
|**/MTd**|`_DEBUG` 및 `_MT`를 정의합니다. 또한, 이 옵션은 컴파일러가 .obj 파일에 라이브러리 이름 LIBCMTD.lib를 배치하여 링커가 LIBCMTD.lib를 사용하여 외부 기호를 확인하도록 만듭니다.|  
|**/LD**|DLL을 만듭니다.<br /><br /> 전달 된 **/DLL** 링커에 옵션입니다. 링커는 `DllMain` 함수를 찾지만 이 함수가 꼭 있어야 하는 것은 아닙니다. `DllMain` 함수를 작성하지 않으면 링커는 TRUE를 반환하는 `DllMain` 함수를 삽입합니다.<br /><br /> DLL 시작 코드를 링크합니다.<br /><br /> 내보내기(.exp) 파일이 명령줄에 지정되지 않은 경우 가져오기 라이브러리(.lib)를 만듭니다. DLL을 호출하는 애플리케이션에 가져오기 라이브러리를 연결합니다.<br /><br /> 해석 [/Fe (EXE 파일 이름)](../../build/reference/fe-name-exe-file.md) .exe 파일이 아닌 DLL 명명 합니다. 기본적으로 프로그램 이름은 됩니다 *basename*대신.dll *basename*.exe입니다.<br /><br /> 의미 **/MT** 명시적으로 지정 하지 않으면 **/MD**합니다.|  
|**/Ldd**|디버그 DLL을 만듭니다. `_MT` 및 `_DEBUG`를 정의합니다.|  
  
 C 런타임 라이브러리 및 사용 하 여 컴파일할 때 사용 되는 라이브러리에 대 한 자세한 내용은 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md), 참조 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)합니다.  
  
 링커의 지정된 된 호출에 전달 되는 모든 모듈은 동일한 런타임 라이브러리 컴파일러 옵션을 사용 하 여 컴파일해야 합니다 (**/MD**, **/MT**, **/LD**).  
  
 런타임 라이브러리의 디버그 버전을 사용 하는 방법에 대 한 자세한 내용은 참조 [C 런타임 라이브러리 참조](../../c-runtime-library/c-run-time-library-reference.md)합니다.  
  
 적절한 C 런타임 라이브러리를 선택하는 방법은 기술 자료 문서 Q140584에서도 설명합니다.  
  
 Dll에 대 한 자세한 내용은 [Visual c + +의 Dll](../../build/dlls-in-visual-cpp.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **코드 생성** 속성 페이지.  
  
4.  수정 된 **런타임 라이브러리** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)