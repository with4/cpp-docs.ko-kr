---
title: "Building an Attributed Program | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tlb files"
  - "MIDL"
  - "MIDL, linker output"
  - "IDL files"
  - "tlb files, building attributed programs"
  - ".tlb files, building attributed programs"
  - "IDL files, building"
  - "attributes [C++], building type libraries and .idl files"
  - ".tlb files"
  - ".idl files, building"
  - "type libraries, linker options for building"
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Building an Attributed Program
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 특성을 소스 코드에 삽입 한 후 형식 라이브러리 및.idl 파일을 생성 하는 Visual C\+\+ 컴파일러를 할 수 있습니다.  다음 링커 옵션을.tlb 및.idl 파일을 빌드할 수 있습니다.  
  
-   [\/IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [\/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [\/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [\/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 일부 프로젝트는 여러 개의 독립적인.idl 파일 포함 됩니다.  둘 이상의.tlb 파일을 생성 하 고 필요한 경우 리소스 블록에 바인딩할이 사용 됩니다.  이 시나리오는 Visual C\+\+의 현재 지원 되지 않습니다.  
  
 또한 Visual C\+\+ 링커는 모든 IDL 관련 특성 정보를 하나의 MIDL 파일을 출력 합니다.  단일 프로젝트에서 두 개의 형식 라이브러리를 생성할 수 있는 방법이 표시 됩니다.  
  
## 참고 항목  
 [Concepts](../windows/attributed-programming-concepts.md)