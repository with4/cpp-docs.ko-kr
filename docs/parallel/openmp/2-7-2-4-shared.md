---
title: 2.7.2.4 공유 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1de0e32e16d889acb8f1339d783bc194b3508dda
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="2724-shared"></a>2.7.2.4 공유됨
이 절에 표시 되는 변수를 공유는 *변수 목록* 이러한 팀의 모든 스레드에서 합니다. 팀에서 모든 스레드는 동일한 저장소 영역에 대 한 액세스 **공유** 변수입니다.  
  
 구문은 **공유** 절은 다음과 같습니다.  
  
```  
shared(variable-list)  
```