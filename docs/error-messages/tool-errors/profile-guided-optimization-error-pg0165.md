---
title: 프로필 기반 최적화 오류 PG0165 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acad97411480112d06dadd454d1368dcfdf2c87f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="profile-guided-optimization-error-pg0165"></a>프로필 기반 최적화 오류 PG0165
읽기 'Filename.pgd': ' PGD 버전이 지원 되지 않습니다 (버전 불일치)'입니다.  
  
 PGD 파일 특정 컴파일러 도구 집합에 적용 됩니다. 이 오류는에 대 한 사용 되는 다른 컴파일러를 사용 하는 경우 발생 *Filename*.pgd 합니다. 이 오류는이 컴파일러 도구 집합에서 데이터를 사용할 수 없습니다 나타냅니다 *Filename*.pgd 현재 프로그램을 최적화할 수 있습니다.  
  
 이 문제를 해결 하려면 재생성 *Filename*.pgd 현재 컴파일러 도구 집합을 사용 하 여 합니다.