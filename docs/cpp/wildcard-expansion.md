---
title: 와일드 카드 확장 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb58d5da479d686cac0d18c9d36e500bd6b5a632
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="wildcard-expansion"></a>와일드카드 식
## <a name="microsoft-specific"></a>Microsoft 전용  
 명령줄에서 파일 이름과 경로 인수를 지정하기 위해 와일드카드, 즉 물음표(?)와 별표(*)를 사용할 수 있습니다.  
  
 명령줄 인수는 호출 하는 루틴에서 처리 **_setargv** (또는 **_wsetargv** 와이드 문자 환경에서)는 에별도문자열로와일드카드를확장하지는기본적으로`argv`문자열 배열을 반환 합니다. 와일드 카드 확장 설정에 대 한 자세한 내용은 참조 [와일드 카드 인수 확장](../c-language/expanding-wildcard-arguments.md)합니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)