---
title: 문자열 초기화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c01dbea3cbcfaf89280f5fd61a31646b88ac491a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383981"
---
# <a name="initializing-strings"></a>문자열 초기화
문자열 리터럴(또는 와이드 문자열 리터럴)로 문자(또는 와이드 문자) 배열을 초기화할 수 있습니다. 예:  
  
```  
char code[ ] = "abc";  
```  
  
 `code`를 네 개의 요소로 이루어진 문자 배열로 초기화합니다. 네 번째 요소는 null 문자로, 모든 문자열 리터럴을 종료합니다.  
  
 식별자 목록의 길이는 초기화될 식별자 수만큼만 가능합니다. 문자열보다 짧은 배열 크기를 지정한 경우 추가 문자는 무시됩니다. 예를 들어, 다음 선언은 `code`를 요소가 3개인 문자 배열로 초기화합니다.  
  
```  
char code[3] = "abcd";  
```  
  
 이니셜라이저의 처음 세 문자만 `code`에 할당됩니다. `d` 문자 및 문자열 종료 null 문자는 무시됩니다. 이는 종료되지 않은 문자열(즉, 끝을 표시하는 0 값이 없는 문자열)을 만들고 이 조건을 나타내는 진단 메시지를 생성합니다.  
  
 선언  
  
```  
char s[] = "abc", t[3] = "abc";  
```  
  
 =  
  
```  
char s[]  = {'a', 'b', 'c', '\0'},   
     t[3] = {'a', 'b', 'c' };  
```  
  
 문자열이 지정된 배열 크기보다 짧은 경우 배열의 나머지 요소는 0으로 초기화됩니다.  
  
 **Microsoft 전용**  
  
 Microsoft C에서 문자열 리터럴은 최대 2048바이트가 될 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [초기화](../c-language/initialization.md)