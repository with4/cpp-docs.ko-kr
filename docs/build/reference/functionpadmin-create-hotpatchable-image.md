---
title: "-FUNCTIONPADMIN (핫 패치 가능 이미지 만들기) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /functionpadmin
dev_langs: C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f737cdb412420ffb87664024b2314941e67b045b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN(핫 패치 가능 이미지 만들기)
핫 패치 가능한 이미지를 준비합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `space`(선택 사항)  
 각 함수의 시작 부분에 추가할 안쪽 여백 크기 5, 6, 또는 16입니다.  x86 이미지에 필요한 5 바이트의 패딩이, x64 이미지에 필요한 6 바이트 및 이미지만 Itanium 프로세서 제품군에 대 한 16 바이트의 패딩이 각 함수의 시작 부분에 필요 합니다.  
  
 기본적으로 컴파일러는 이미지의 컴퓨터 종류에 따라 이미지에 올바른 양의 공간을 추가 합니다.  
  
 핫 패치 가능 이미지를 생성 하도록 링커에 대 한 순서로.obj 파일 컴파일해야와 [/hotpatch (핫 패치 가능 이미지 만들기)](../../build/reference/hotpatch-create-hotpatchable-image.md)합니다.  
  
 컴파일 및 cl.exe 한 번 호출을 사용 하 여 이미지를 연결 하는 경우 **/hotpatch** 의미 **/functionpadmin**합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)