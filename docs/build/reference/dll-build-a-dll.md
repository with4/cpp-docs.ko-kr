---
title: "-DLL (DLL 빌드) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /dll
dev_langs: C++
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6ca732d96eaa0ae7e4ffd805063156be519d41ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="dll-build-a-dll"></a>/DLL(DLL 빌드)
```  
/DLL  
```  
  
## <a name="remarks"></a>설명  
 /DLL 옵션 주 출력 파일로 DLL을 빌드합니다. 일반적으로 DLL에는 다른 프로그램에서 사용할 수 있는 내보내기 포함 되어 있습니다. 권장된 사용 순서 대로 나열 된 export를 지정 하기 위한 세 가지가 있습니다.  
  
1.  [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) 소스 코드에서  
  
2.  [내보내기](../../build/reference/exports.md) .def 파일에서 문  
  
3.  [/내보내기](../../build/reference/export-exports-a-function.md) LINK 명령의 사양  
  
 프로그램 둘 이상의 메서드를 사용할 수 있습니다.  
  
 또 다른 방법은 dll을 **라이브러리** 모듈 정의 문의 합니다. /BASE 및 /DLL 옵션이 모두 해당 하는 **라이브러리** 문.  
  
 개발 환경;이 옵션을 지정 하지 않으면 이 옵션은 명령줄 에서만 사용 됩니다. 이 옵션은 응용 프로그램 마법사로 DLL 프로젝트를 만들 때 설정 됩니다.  
  
 Note.dll을 만들기 전에 예비 단계에서 가져오기 라이브러리를 만드는 경우 전달 해야 합니다 개체 파일의 동일한 집합.dll을 빌드할 때 가져오기 라이브러리를 빌드할 때 성공 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **구성 속성** 폴더입니다.  
  
3.  클릭는 **일반** 속성 페이지.  
  
4.  수정 된 **구성 유형을** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)