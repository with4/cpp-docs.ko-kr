---
title: "2.7.2.4 공유 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4320a3df64d8056cf1c8657acc78281f56cd1c85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="2724-shared"></a>2.7.2.4 공유됨
이 절에 표시 되는 변수를 공유는 *변수 목록* 이러한 팀의 모든 스레드에서 합니다. 팀에서 모든 스레드는 동일한 저장소 영역에 대 한 액세스 **공유** 변수입니다.  
  
 구문은 **공유** 절은 다음과 같습니다.  
  
```  
shared(variable-list)  
```