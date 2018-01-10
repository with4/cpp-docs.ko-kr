---
title: "-DEFAULTLIB (기본 라이브러리 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs: C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40fe07543dd9dc65d93cc9f79504f5fd324204dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB(기본 라이브러리 지정)
```  
/DEFAULTLIB:library  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *라이브러리*  
 외부 참조를 확인할 때 검색할 라이브러리의 이름입니다.  
  
## <a name="remarks"></a>설명  
 /DEFAULTLIB 옵션에는 추가 *라이브러리* 참조를 확인할 때 링크를 검색 하는 라이브러리 목록에 있습니다. 명령줄에서.obj 파일에 지정 된 기본 라이브러리 하기 전에 지정 된 라이브러리 후 /DEFAULTLIB으로 지정 된 라이브러리를 검색 합니다.  
  
 [모든 기본 라이브러리 무시](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB) 옵션 무시 /DEFAULTLIB:*라이브러리*합니다. [라이브러리 무시](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB:*라이브러리*) 옵션 무시 /DEFAULTLIB:*라이브러리* 때 동일한 *라이브러리* 이름이 둘 다에 지정 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
-   Visual Studio 개발 환경에서이 링커 옵션 ´ ù. 라이브러리에 링크 단계를 추가 하려면 사용 하 여는 **추가 종속성** 속성은 **입력** 속성 페이지.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)