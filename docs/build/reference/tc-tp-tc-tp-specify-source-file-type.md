---
title: "-Tc,-Tp,-/TC,-TP (소스 파일 형식 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs: C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69ccd08967d386780744fb85476033430127ba3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP(소스 파일 형식 지정)
**/Tc** 옵션을 지정 하는 `filename` 위치에.c 확장명 없는 하는 경우에 C 소스 파일입니다. **/Tp** 옵션을 지정 하는 `filename` .cpp 또는.cxx 확장명 없는 경우에 c + + 소스 파일을입니다. 옵션 사이 공백 및 `filename` 선택 사항입니다. 하나의 파일을 지정 하는 각 옵션 추가 파일을 지정 하려면 옵션을 반복 합니다.  
  
 **/TC** 및 **/TP** 의 전역 테스트가 **/Tc** 및 **/Tp**합니다. C 소스 파일로 명령줄의 모든 파일을 처리 하도록 컴파일러에 지정 (**/TC**) 또는 c + + 소스 파일 (**/TP**), 해당 옵션과 관련 된 명령줄에서 위치에 관계 없이 합니다. 방법으로 단일 파일에서 이러한 전역 옵션을 재정의할 수 있습니다 **/Tc** 또는 **/Tp**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 C 또는 c + + 소스 파일.  
  
## <a name="remarks"></a>설명  
 기본적으로 CL.c 확장명을 가진 파일은 C 소스 파일 및.cpp 또는.cxx 확장명을 사용 하 여 파일은 c + + 소스 파일을 가정 합니다.  
  
 경우 중 하나는 **TC** 또는 **Tc** 옵션을 지정의 사양을 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 옵션은 무시 됩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **컴파일** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>을 참조하세요.  
  
## <a name="examples"></a>예제  
 다음 CL 명령줄은 모든 C 소스 파일을 MAIN.c, TEST.prg, 및 COLLATE.prg가 되도록 지정 합니다. CL PRINT.prg 인식 되지 않습니다.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 다음 CL 명령줄 c + + 파일로 컴파일된 TEST1.c, TEST2.cxx, TEST3.huh, 및 TEST4.o TEST5.z 파일을 C로 컴파일된 지정 합니다.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)