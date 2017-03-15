---
title: "/LARGEADDRESSAWARE(큰 주소 처리) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.LargeAddressAware"
  - "/largeaddressaware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LARGEADDRESSAWARE 링커 옵션"
  - "LARGEADDRESSAWARE 링커 옵션"
  - "-LARGEADDRESSAWARE 링커 옵션"
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /LARGEADDRESSAWARE(큰 주소 처리)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## 설명  
 \/LARGEADDRESSAWARE 옵션을 사용하면 응용 프로그램에서 2GB보다 큰 주소를 처리할 수 있도록 링커에 지시할 수 있습니다.  64비트 컴파일러에서는 이 옵션이 기본적으로 사용됩니다.  32비트 컴파일러에서 링커 줄에 \/LARGEADDRESSAWARE가 다르게 지정되어 있지 않으면 기본적으로 \/LARGEADDRESSAWARE:NO가 사용됩니다.  
  
 \/LARGEADDRESSAWARE를 사용하여 응용 프로그램을 링크한 경우에는 DUMPBIN [\/HEADERS](../../build/reference/headers.md)에서 그 결과에 대한 정보를 표시합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **시스템** 속성 페이지를 클릭합니다.  
  
4.  **큰 주소 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)