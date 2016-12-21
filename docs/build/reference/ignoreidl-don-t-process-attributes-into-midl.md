---
title: "/IGNOREIDL(특성을 MIDL로 처리하지 않음) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.IgnoreEmbeddedIDL"
  - "/ignoreidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNOREIDL 링커 옵션"
  - "IGNOREIDL 링커 옵션"
  - "-IGNOREIDL 링커 옵션"
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IGNOREIDL(특성을 MIDL로 처리하지 않음)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNOREIDL  
```  
  
## 설명  
 \/IGNOREIDL 옵션을 사용하면 소스 코드 내의 모든 [IDL 특성](../../windows/idl-attributes.md)이 .idl 파일로 처리되지 않도록 지정할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **포함 IDL** 속성 페이지를 클릭합니다.  
  
4.  **포함 IDL 무시** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [\/IDLOUT\(MIDL 출력 파일 이름 지정\)](../../build/reference/idlout-name-midl-output-files.md)   
 [\/TLBOUT\(.TLB 파일 이름 지정\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [\/MIDL\(MIDL 명령줄 옵션 지정\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)