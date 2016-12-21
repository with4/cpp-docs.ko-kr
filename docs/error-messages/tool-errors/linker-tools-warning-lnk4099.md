---
title: "링커 도구 경고 LNK4099 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4099"
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' PDB를 'object\/library' 또는 'path'에서 찾을 수 없습니다. 디버그 정보가 없는 것처럼 개체를 링크합니다.  
  
 링커가 .pdb 파일을 찾지 못했습니다.  이 파일을 `object/library`가 포함된 디렉터리에 복사하십시오.  
  
 개체 파일과 연결된 .pdb 파일의 이름을 찾으려면  
  
1.  [lib](../../build/reference/lib-reference.md) **\/extract:**`objectname`**.obj** `xyz`**.lib**를 사용하여 라이브러리에서 개체 파일을 추출합니다.  
  
2.  **dumpbin \/section:.debug$T \/rawdata**  `objectname` **.obj**를 사용하여 .pdb 파일의 경로를 확인합니다.  
  
 링크하는 개체에 대한 .pdb 파일이 없는 경우, pdb를 사용할 필요가 없도록 [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)로 컴파일하거나 [\/DEBUG](../../build/reference/debug-generate-debug-info.md) 링커 옵션을 제거할 수도 있습니다.