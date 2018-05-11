---
title: 범위 읽기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8ebad4bfda77238ad8c861410e2af5453df73af
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
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