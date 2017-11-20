---
title: "와일드카드 인수 확장명 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0c1deca52e74241b56c3c152e66a74d652b4829
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="expanding-wildcard-arguments"></a>와일드카드 인수 확장명
**Microsoft 전용**  
  
 C 프로그램을 실행할 때 물음표(?)와 별표(*) 중 하나를 와일드카드로 사용하여 명령줄에서 파일 이름 및 경로 인수를 지정할 수 있습니다.  
  
 기본적으로 명령줄 인수에서는 와일드카드가 확장되지 않습니다. 일반 인수 벡터 `argv` 로드 루틴을 setargv.obj 또는 wsetargv.obj 파일과 연결하여 와일드카드를 확장하는 버전으로 바꿀 수 있습니다. 프로그램에서 `main` 함수를 사용하는 경우 setargv.obj와 연결합니다. 프로그램에서 `wmain` 함수를 사용하는 경우 wsetargv.obj와 연결합니다. 이 두 동작은 동일한 동작입니다.  
  
 setargv.obj 또는 wsetargv.obj와 연결하려면 **/link** 옵션을 사용합니다. 예:  
  
 **cl example.c /link setargv.obj**  
  
 운영 체제 명령과 같은 방식으로 와일드카드가 확장됩니다. 와일드카드에 대해 잘 모를 경우 운영 체제 사용자 가이드를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [링크 옵션](../c-runtime-library/link-options.md)   
 [main 함수 및 프로그램 실행](../c-language/main-function-and-program-execution.md)