---
title: "/MERGE(섹션 결합) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/merge"
  - "VC.Project.VCLinkerTool.MergeSections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MERGE 링커 옵션"
  - "MERGE 링커 옵션"
  - "-MERGE 링커 옵션"
  - "섹션"
  - "섹션, 결합"
  - "섹션, 명명"
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MERGE(섹션 결합)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MERGE:from=to  
```  
  
## 설명  
 \/MERGE 옵션을 사용하면 첫 번째 섹션\(*from*\)이 두 번째 섹션\(*to*\)과 결합되고 결과 섹션의 이름이 *to*로 지정됩니다.  예를 들면 `/merge:.rdata=.text`와 같습니다.  
  
 두 번째 섹션이 없으면 LINK에서는 *from* 섹션의 이름을 *to*로 바꿉니다.  
  
 \/MERGE 옵션은 VxD를 만들고 컴파일러가 생성한 섹션 이름을 재정의할 때 유용합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **섹션 병합** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)