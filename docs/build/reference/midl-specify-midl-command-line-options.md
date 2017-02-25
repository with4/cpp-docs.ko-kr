---
title: "/MIDL(MIDL 명령줄 옵션 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/midl"
  - "VC.Project.VCLinkerTool.MidlCommandFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MIDL 링커 옵션"
  - "MIDL"
  - "MIDL 링커 옵션"
  - "-MIDL 링커 옵션"
  - "MIDL, 명령줄 옵션"
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MIDL(MIDL 명령줄 옵션 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MIDL:@file  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `file`  
 [MIDL command line options](http://msdn.microsoft.com/library/windows/desktop/aa366839)이 포함된 파일의 이름입니다.  
  
## 설명  
 IDL 파일을 TLB 파일로 변환할 때 사용하는 모든 옵션이 `file`에 지정되어 있어야 합니다. MIDL 명령줄 옵션은 링커의 명령줄에서 지정할 수 없습니다.  \/MIDL을 지정하지 않으면 MIDL 컴파일러는 다른 옵션이 없는 상태에서 IDL 파일 이름만 사용하여 호출됩니다.  
  
 이 파일의 각 줄에는 하나의 MIDL 명령줄 옵션이 있어야 합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **포함 IDL** 속성 페이지를 클릭합니다.  
  
4.  **MIDL 명령** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [\/IDLOUT\(MIDL 출력 파일 이름 지정\)](../../build/reference/idlout-name-midl-output-files.md)   
 [\/IGNOREIDL\(특성을 MIDL로 처리하지 않음\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/TLBOUT\(.TLB 파일 이름 지정\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)