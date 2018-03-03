---
title: "범위 읽기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36fd3354e21b063dba05e24e1e3ba0d206a89343
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="reading-ranges"></a>범위 읽기
**ANSI 4.9.6.2** `fscanf` 함수에서 % [ 변환을 위한 scanlist의 첫 번째 문자도 아니고 마지막 문자도 아닌 대시(–) 문자의 해석  
  
 다음 줄  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 에서는 A–Z 범위에 속한 문자의 개수를 `strptr`이 가리키는 문자열로 읽습니다.  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)