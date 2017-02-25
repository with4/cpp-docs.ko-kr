---
title: "/ALIGN(섹션 맞춤) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Alignment"
  - "/align"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALIGN 링커 옵션"
  - "ALIGN 링커 옵션"
  - "-ALIGN 링커 옵션"
  - "섹션 맞춤"
  - "섹션"
  - "섹션, 맞춤 지정"
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /ALIGN(섹션 맞춤)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALIGN[:number]  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `number`  
 맞춤 값입니다.  
  
## 설명  
 \/ALIGN 옵션은 프로그램의 선형 주소 공간 내에서 각 섹션의 맞춤을 지정합니다.  `number` 인수는 바이트 단위로 지정하며 2의 배수이어야 합니다.  기본값은 4K\(4096\)입니다.  링커에서는 맞춤으로 인해 잘못된 이미지가 생성되는 경우 경고를 표시합니다.  
  
 장치 드라이버 등의 응용 프로그램을 작성하는 경우가 아니면 맞춤을 수정할 필요는 없습니다.  
  
 [\/SECTION](../../build/reference/section-specify-section-attributes.md) 옵션에 맞춤 매개 변수를 사용하여 특정 섹션의 맞춤을 수정할 수 있습니다.  
  
 지정한 맞춤 값은 가장 큰 섹션 맞춤 이상이어야 합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)