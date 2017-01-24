---
title: "/HEAP(힙 크기 설정) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.HeapCommitSize"
  - "/heap"
  - "VC.Project.VCLinkerTool.HeapReserveSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HEAP 링커 옵션"
  - "힙 할당, 힙 크기 설정"
  - "HEAP 링커 옵션"
  - "-HEAP 링커 옵션"
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HEAP(힙 크기 설정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/HEAP:reserve[,commit]  
```  
  
## 설명  
 \/HEAP 옵션은 힙 크기를 바이트 단위로 설정합니다.  이 옵션은 .exe 파일을 빌드할 때만 사용합니다.  
  
 *reserve* 인수는 가상 메모리에서 전체 힙 할당을 지정합니다.  기본 힙 크기는 1MB입니다.  그러면 링커에서는 지정된 값을 가장 가까운 4바이트 단위 값으로 반올림합니다.  
  
 선택적인 `commit` 인수는 운영 체제에서 해석됩니다.  Windows NT\/Windows 2000에서 이 인수는 한 번에 할당할 실제 메모리 양을 지정합니다.  커밋된 가상 메모리는 페이징 파일에 공간을 예약합니다.  `commit` 값이 크면 응용 프로그램에 더 많은 힙 공간이 필요할 때 시간을 절약할 수 있지만 메모리 요구량과 시작 시간은 늘어날 수 있습니다.  
  
 *reserve* 및 `commit` 값은 십진법 또는 C 언어 표기법으로 지정합니다.  
  
 이 기능은 [HEAPSIZE](../../build/reference/heapsize.md)를 사용하는 모듈 정의 파일을 통해 사용할 수도 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **시스템** 속성 페이지를 클릭합니다.  
  
4.  **힙 커밋 크기** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)