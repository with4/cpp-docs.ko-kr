---
title: -IMPLIB (가져오기 라이브러리 이름) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72edc0fcb1b216319d6f6c9924cb92a165b3196b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="implib-name-import-library"></a>/IMPLIB(가져오기 라이브러리 이름 지정)
  
> /IMPLIB:*파일 이름*  
  
## <a name="parameters"></a>매개 변수  
  
*filename*  
가져오기 라이브러리에 대 한 사용자 지정 이름입니다. 기본 이름을 대체합니다.  
  
## <a name="remarks"></a>설명  
  
/IMPLIB 옵션 내보내기가 포함 된 프로그램을 빌드할 때 링크를 만드는 가져오기 라이브러리에 대 한 기본 이름을 재정의 합니다. 기본 이름은 기본 출력 파일 및 확장의 기본 이름에서 형성 됩니다. lib 합니다. 다음 중 하나 이상의 지정 된 경우 내보내기를 포함 하는 프로그램:  
  
-   [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드의 키워드  
  
-   [내보내기](../../build/reference/exports.md) .def 파일에서 문  
  
-   [/내보내기](../../build/reference/export-exports-a-function.md) LINK 명령의 사양  
  
 가져오기 라이브러리가 생성 될 때 /IMPLIB을 무시 합니다. 내보내기가 없거나 지정 된 경우 링크 가져오기 라이브러리를 만들지 않습니다. 빌드에는 내보내기 파일을 사용 하는 경우 링크도 간주 한 가져오기 라이브러리 이미 존재 만들지 않습니다. 가져오기 라이브러리 및 내보내기 파일에 대 한 정보를 참조 하십시오. [LIB 참조](../../build/reference/lib-reference.md)합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **가져오기 라이브러리** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)