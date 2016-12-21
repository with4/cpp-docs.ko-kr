---
title: "/SWAPRUN(링커 출력을 스왑 파일로 로드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.SwapRunFromNet"
  - "/swaprun"
  - "VC.Project.VCLinkerTool.SwapRunFromCD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN 링커 옵션"
  - "파일[C++], LINK"
  - "LINK 도구[C++], 출력"
  - "링커[C++], 스왑 파일에 출력 복사"
  - "출력 파일, 링커"
  - "링커 출력을 위한 스왑 파일"
  - "SWAPRUN 링커 옵션"
  - "-SWAPRUN 링커 옵션"
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SWAPRUN(링커 출력을 스왑 파일로 로드)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{NET|CD}  
```  
  
## 설명  
 \/SWAPRUN 옵션을 사용하면 운영 체제에서는 먼저 링커 출력을 스왑 파일로 복사한 다음 스왑 파일에서 이미지를 실행합니다.  이 기능은 Windows NT 4.0 이상의 기능입니다.  
  
 NET가 지정되어 있으면 운영 체제에서는 먼저 네트워크의 이진 이미지를 스왑 파일로 복사한 다음 스왑 파일에서 해당 이미지를 로드합니다.  이 옵션은 네트워크를 통해 응용 프로그램을 실행할 때 유용합니다.  CD가 지정되어 있으면 운영 체제에서는 이동식 디스크에 있는 이미지를 페이지 파일로 복사한 다음 로드합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **시스템** 속성 페이지를 클릭합니다.  
  
4.  다음 속성 중 하나를 수정합니다.  
  
    -   **CD에서 스왑 실행**  
  
    -   **Network에서 스왑 실행**  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> 속성을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)