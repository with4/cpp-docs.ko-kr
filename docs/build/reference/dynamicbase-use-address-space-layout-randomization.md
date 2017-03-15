---
title: "/DYNAMICBASE(주소 공간 레이아웃을 임의로 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RandomizedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE 링커 옵션"
  - "DYNAMICBASE 링커 옵션"
  - "-DYNAMICBASE 링커 옵션"
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /DYNAMICBASE(주소 공간 레이아웃을 임의로 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로드할 때 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]의 ASLR\(Address Space Layout Randomization\) 기능을 사용하여 임의로 기준 주소를 지정할 수 있는 실행 가능 이미지를 생성할지 여부를 지정합니다.  
  
## 구문  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## 설명  
 \/DYNAMICBASE는 기본적으로 사용됩니다.  
  
 이 옵션은 실행 파일의 헤더를 수정하여 로드 시 응용 프로그램의 주소가 임의로 지정되어야 하는지를 나타냅니다.  
  
 주소 공간 레이아웃 불규칙화는 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]에서 지원됩니다.  
  
### Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **고급** 속성 페이지를 선택합니다.  
  
5.  **임의 기준 주소** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)