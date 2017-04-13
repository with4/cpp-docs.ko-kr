---
title: "컴파일러 경고 (수준 1) C4952 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fa48ab2f0e7a2a9d7675af5d2e88aa56b100f022
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4952"></a>컴파일러 경고(수준 1) C4952
'function': 프로그램 데이터베이스 'pgd_file'에 프로필 데이터가 없습니다.  
  
 사용 하는 경우 [/ltcg: pgupdate](../../build/reference/ltcg-link-time-code-generation.md), 컴파일러는 이후 다시 컴파일 입력된 모듈을 검색 했습니다. `/LTCG:PGINSTRUMENT` 에 새 함수 (***함수***) 존재 합니다.  
  
 이 경고는 정보 제공용입니다. 이 경고를 해결하려면 `/LTCG:PGINSTRUMENT`를 실행하고 모든 테스트 실행을 다시 수행한 다음 `/LTCG:PGOPTIMIZE`를 실행해야 합니다.  
  
 `/LTCG:PGOPTIMIZE` 를 사용한 경우 이 경고는 오류로 대체됩니다.
