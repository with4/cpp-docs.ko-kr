---
title: "/IDLOUT(MIDL 출력 파일 이름 지정) | Microsoft Docs"
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
  - "/idlout"
  - "VC.Project.VCLinkerTool.MergedIDLBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".idl 파일, 경로"
  - "/IDLOUT 링커 옵션"
  - "IDL 파일, 경로"
  - "IDLOUT 링커 옵션"
  - "-IDLOUT 링커 옵션"
  - "MIDL"
  - "MIDL, 출력 파일 이름"
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IDLOUT(MIDL 출력 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IDLOUT:[path\]filename  
```  
  
## 매개 변수  
 *path*  
 절대 또는 상대 경로입니다.  경로를 지정하면 .idl 파일의 위치만 변경되며 다른 모든 파일은 프로젝트 디렉터리에 있습니다.  
  
 *filename*  
 MIDL 컴파일러에서 만든 .idl 파일의 이름을 지정합니다.  기본적으로 사용되는 파일 확장명은 없으므로 .idl 확장명을 사용하려면 *filename*.idl을 지정합니다.  
  
## 설명  
 \/IDLOUT 옵션은 .idl 파일의 이름과 확장명을 지정합니다.  
  
 MIDL 컴파일러는 Visual C\+\+ 링커에서 [module](../../windows/module-cpp.md) 특성이 포함된 프로젝트를 링크할 때 호출됩니다.  
  
 \/IDLOUT은 MIDL 컴파일러와 연관된 다음의 기타 출력 파일 이름도 지정합니다.  
  
-   *filename*.tlb  
  
-   *filename*\_p.c  
  
-   *filename*\_i.c  
  
-   *filename*.h  
  
 *filename*은 \/IDLOUT에 전달되는 매개 변수입니다.  [\/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)이 지정되어 있으면 .tlb 파일은 \/TLBOUT *filename*에서 해당 이름을 가져옵니다.  
  
 \/IDLOUT과 \/TLBOUT을 모두 지정하지 않으면 링커에서는 vc70.tlb, vc70.idl, vc70\_p.c, vc70\_i.c 및 vc70.h를 만듭니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **포함 IDL** 속성 페이지를 클릭합니다.  
  
4.  **병합 IDL 기본 파일 이름** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [\/IGNOREIDL\(특성을 MIDL로 처리하지 않음\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL\(MIDL 명령줄 옵션 지정\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)