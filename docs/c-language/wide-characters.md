---
title: 와이드 문자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- wide characters
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf20b58ad9343f1a90f07a7f4c07bccd397a5888
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386640"
---
# <a name="wide-characters"></a>와이드 문자
**ANSI 3.1.3.4** 둘 이상의 문자를 포함하는 정수 문자 상수 또는 둘 이상의 멀티바이트 문자를 포함하는 와이드 문자 상수의 값입니다.  
  
 일반 문자 상수인 'ab'의 정수 값은 (int)0x6162입니다. 문자가 2바이트 이상이면 이전에 읽은 바이트가 **CHAR_BIT**의 값만큼 왼쪽으로 이동되며 낮은 **CHAR_BIT** 비트가 포함된 비트 OR 연산자를 사용하여 다음 바이트를 비교합니다. 멀티바이트 문자 상수의 바이트 수는 sizeof(int)를 초과할 수 없습니다. 32비트 대상 코드의 경우 sizeof(int)는 4입니다.  
  
 위에서 설명한 것처럼 멀티바이트 문자 상수를 읽은 다음 `mbtowc` 런타임 함수를 사용하여 와이드 문자 상수로 변환합니다. 변환 결과가 유효한 와이드 문자 상수가 아니면 오류가 발생합니다. 어떠한 경우에도 `mbtowc` 함수가 검사하는 바이트 수는 `MB_CUR_MAX`의 값으로 제한됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [문자](../c-language/characters.md)