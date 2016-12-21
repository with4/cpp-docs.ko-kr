---
title: "/TLBOUT(.TLB 파일 이름 지정) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.TypeLibraryFile"
  - "/tlbout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".tlb 파일, 이름 바꾸기"
  - "/TLBOUT 링커 옵션"
  - "tlb 파일, 이름 바꾸기"
  - "TLBOUT 링커 옵션"
  - "-TLBOUT 링커 옵션"
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLBOUT(.TLB 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBOUT:[path\]filename  
```  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *path*  
 .tlb 파일을 만들 절대 또는 상대 경로입니다.  
  
 *filename*  
 MIDL 컴파일러에서 만든 .tlb 파일의 이름을 지정합니다.  기본적으로 사용되는 파일 확장명은 없으므로 .tlb 확장명을 사용하려면 *filename*.tlb를 지정합니다.  
  
## 설명  
 \/TLBOUT 옵션은 .tlb 파일의 이름과 확장명을 지정합니다.  
  
 MIDL 컴파일러는 Visual C\+\+ 링커에서 [module](../../windows/module-cpp.md) 특성이 포함된 프로젝트를 링크할 때 호출됩니다.  
  
 \/TLBOUT이 지정되어 있지 않으면 .tlb 파일은 [\/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*에서 해당 이름을 가져옵니다.  \/IDLOUT이 지정되지 않은 경우 .tlb 파일의 이름은 vc70.tlb가 됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **포함 IDL** 속성 페이지를 클릭합니다.  
  
4.  **형식 라이브러리** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [\/IGNOREIDL\(특성을 MIDL로 처리하지 않음\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL\(MIDL 명령줄 옵션 지정\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)