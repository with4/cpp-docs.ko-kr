---
title: 형식 검사 (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 959dd52847e6140667671b9992471155d68e9646
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="type-checking-crt"></a>형식 검사(CRT)
컴파일러는 아래와 같이 다양한 수의 인수를 사용할 수 있는 함수에서 제한된 형식 검사를 수행합니다.  
  
|함수 호출 |형식이 검사된 인수|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|첫 번째 인수(형식 문자열)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|처음 두 개의 인수(파일 또는 버퍼 및 형식 문자열)|  
|`_snprintf_s`|처음 세 개의 인수(파일 또는 버퍼, 개수 및 형식 문자열)|  
|`_open`|처음 두 개의 인수(경로 및 `_open` 플래그)|  
|`_sopen_s`|처음 세 개의 인수(경로, `_open` 플래그 및 공유 모드)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|처음 두 개의 인수(경로 첫 번째 인수 포인터)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|처음 세 개의 인수(모드 플래그, 경로 및 첫 번째 인수 포인터)|  
  
 컴파일러는 이러한 함수의 와이드 문자 대응에서 같은 제한된 형식 검사를 수행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)