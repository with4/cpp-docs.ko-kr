---
title: "식의 배열 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29f6e16e665d8076ed5a1fe593e1bb9437f1406a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="arrays-in-expressions"></a>식의 배열
배열 형식의 식별자 표시 되 면 식 이외의 `sizeof`의 주소 (**&**), 또는 초기화 대 한 참조의 첫 번째 배열 요소에 대 한 포인터로 변환 됩니다. 예:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 `psz` 포인터는 `szError1` 배열의 첫 번째 요소를 가리킵니다. 포인터와 달리 배열은 수정할 수 있는 l-value가 아닙니다. 따라서 다음 대입은 올바르지 않습니다.  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>참고 항목  
 [배열](../cpp/arrays-cpp.md)