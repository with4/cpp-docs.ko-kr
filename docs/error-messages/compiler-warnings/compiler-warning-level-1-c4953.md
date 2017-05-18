---
title: "컴파일러 경고 (수준 1) C4953 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d0b8ba97d493cb6e840be1023f7c6bd29a5cbd1a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4953"></a>컴파일러 경고(수준 1) C4953
프로필 데이터가 수집된 이후 'function' 인라인이 편집되었습니다. 프로필 데이터가 사용되지 않습니다.  
  
 사용 하는 경우 [/ltcg: pgupdate](../../build/reference/ltcg-link-time-code-generation.md), 컴파일러는 이후 다시 컴파일 입력된 모듈을 검색 했습니다. `/LTCG:PGINSTRUMENT` 에 함수 (***함수***) 편집 하 고 함수에 대 한 후보로 식별 된 기존 테스트 실행 인라인 처리 합니다. 그러나 모듈을 다시 컴파일하면 함수가 더 이상 인라인 후보가 아닙니다.  
  
 이 경고는 정보 제공용입니다. 이 경고를 해결하려면 `/LTCG:PGINSTRUMENT`를 실행하고 모든 테스트 실행을 다시 수행한 다음 `/LTCG:PGOPTIMIZE`를 실행해야 합니다.  
  
 `/LTCG:PGOPTIMIZE` 를 사용한 경우 이 경고는 오류로 대체됩니다.
