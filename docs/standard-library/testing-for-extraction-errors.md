---
title: "추출 오류 테스트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "추출 오류"
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 추출 오류 테스트
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Output error processing functions, discussed in [Error Processing Functions](../standard-library/output-file-stream-member-functions.md), apply to input streams.  Testing for errors during extraction is important.  Consider this statement:  
  
```  
cin >> n;  
```  
  
 If `n` is a signed integer, a value greater than 32,767 \(the maximum allowed value, or MAX\_INT\) sets the stream's `fail` bit, and the `cin` object becomes unusable.  All subsequent extractions result in an immediate return with no value stored.  
  
## 참고 항목  
 [Input Streams](../standard-library/input-streams.md)