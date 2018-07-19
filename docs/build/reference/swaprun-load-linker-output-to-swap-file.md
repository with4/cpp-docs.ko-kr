---
title: -SWAPRUN (부하 링커 출력을 스왑 파일로) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
dev_langs:
- C++
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 522cd693da1b4e1a72d11119f622d862413b409b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377419"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN(링커 출력을 스왑 파일로 로드)
```  
/SWAPRUN:{NET|CD}  
```  
  
## <a name="remarks"></a>설명  
 /SWAPRUN 옵션 링커가 첫 번째 복사 하도록 운영 체제의 스왑 파일에 출력 한 후 여기에서 이미지를 실행 합니다. 이 기능은 Windows NT 4.0 (이상)입니다.  
  
 NET가 지정 하는 경우 운영 체제 먼저 이진 이미지 네트워크에서 스왑 파일에 복사한 위치에서 로드 합니다. 이 옵션은 네트워크를 통해 응용 프로그램을 실행 하는 데 유용 합니다. CD가 지정 운영 체제를 복사 하는 이동식 디스크에 있는 이미지를 페이지 파일로 다음 로드 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **시스템** 속성 페이지.  
  
4.  다음 속성 중 하나를 수정 합니다.  
  
    -   **CD에서 스왑 실행**  
  
    -   **네트워크에서 스왑 실행**  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> 속성을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)