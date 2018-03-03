---
title: "특성이 지정 된 프로그램을 빌드할 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3e39bbd2b630d35942c1c5107041b2fbadf7549
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="building-an-attributed-program"></a>특성을 사용하는 프로그램 빌드
소스 코드에 Visual c + + 특성을 추가한 후에 사용자에 대 한 형식 라이브러리 및.idl 파일을 생성 하 고 Visual c + + 컴파일러를 할 수 있습니다. 다음의 링커 옵션.tlb 및.idl 파일을 빌드할 수 있습니다.  
  
-   [/IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 일부 프로젝트에는 여러 독립적인.idl 파일이 있습니다. 이러한 작업은 두 개 이상의.tlb 파일을 생성 하 고 필요에 따라 리소스 블록에 바인딩해야 하는 데 사용 됩니다. 이 시나리오는 Visual c + +에서 현재 지원 되지 않습니다.  
  
 또한 Visual c + + 링커는 모든 IDL 관련 특성 정보를 단일 MIDL 파일로 출력 합니다. 단일 프로젝트에서 두 개의 형식 라이브러리를 생성할 수 없으므로가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../windows/attributed-programming-concepts.md)