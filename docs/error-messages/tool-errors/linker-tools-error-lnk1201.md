---
title: "링커 도구 오류 LNK1201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1201"
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 오류 LNK1201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 프로그램 데이터베이스를 쓰는 동안 오류가 발생했습니다. 디스크 공간이 부족한지, 경로가 잘못되었는지 또는 권한이 없는지 확인하십시오.  
  
 LINK가 출력 파일의 PDB\(프로그램 데이터베이스\)에 쓰지 못했습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  파일이 손상되었습니다.  PDB 파일을 삭제하고 다시 링크하십시오.  
  
2.  디스크 공간이 부족하여 파일을 쓸 수 없습니다.  
  
3.  네트워크 문제로 인해 드라이브를 사용할 수 없습니다.  
  
4.  연결을 시도 중인 프로그램에 디버거가 활성화되어 있습니다.  
  
5.  힙 공간이 부족합니다.  자세한 내용은 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)을 참조하십시오.