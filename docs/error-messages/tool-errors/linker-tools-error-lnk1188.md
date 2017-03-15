---
title: "링커 도구 오류 LNK1188 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1188"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1188"
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 링커 도구 오류 LNK1188
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BADFIXUPSECTION:: 'symbol' 픽스업 대상이 잘못되었습니다. 길이 섹션이 0입니다.  
  
 VxD 링크 중에 재배치의 대상에 섹션이 없었습니다.  LINK386\(이전 버전\)에서는 길이가 0인 섹션을 길이가 0이 아닌 섹션과 결합하는 데 OMF GROUP 레코드\(MASM GROUP 지시문에 의해 생성\)를 사용할 수 있었습니다.  COFF 형식은 GROUP 지시문과 길이가 0인 섹션을 지원하지 않습니다.  LINK가 이 형식의 OMF 개체를 COFF로 자동 변환할 때 이 오류가 발생할 수 있습니다.