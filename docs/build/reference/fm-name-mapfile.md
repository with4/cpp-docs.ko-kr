---
title: "-Fm (맵 파일 이름) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /fm
dev_langs:
- C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a5111291ea92b8650896faf3117f0056510e5ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fm-name-mapfile"></a>/Fm(맵 파일 이름 지정)
세그먼트에 해당 하는.exe 파일 또는 DLL에 있는 순서 대로 목록을 포함 하는 맵 파일을 만들도록 링커에 지시할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Fmpathname  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 맵 파일의 해당 C 또는 c + + 소스 파일의 기본 이름 지정 되는 합니다. 확장을 매핑하십시오.  
  
 지정 **/Fm** 를 지정한 경우에 따라 같은 효과가 [/MAP (맵 파일 생성)](../../build/reference/map-generate-mapfile.md) 링커 옵션입니다.  
  
 지정 하는 경우 [(컴파일 없이 링크 사용) /c](../../build/reference/c-compile-without-linking.md) 링크 하지 않도록 하려면 **/Fm** 영향을 주지 않습니다.  
  
 컴파일러를 변수 이름에 선행 밑줄이 추가 하기 때문에 일반적으로 전역 기호 맵 파일에는 하나 이상의 선행 밑줄이 있습니다. 맵 파일에 표시 되는 많은 전역 기호는 컴파일러 및 표준 라이브러리에서 내부적으로 사용 됩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)