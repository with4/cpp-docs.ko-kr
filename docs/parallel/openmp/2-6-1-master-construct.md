---
title: "2.6.1 master 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bff566967749068f9792a98dc3cf2151e4df3d9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="261-master-construct"></a>2.6.1 master 구문
**마스터** 지시문 팀의 마스터 스레드에 의해 실행 되는 구조화 된 블록을 지정 하는 구조를 식별 합니다. 구문은 **마스터** 지시문은 다음과 같습니다.  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 팀의 다른 스레드를 연결된 하는 구조화 된 블록을 실행 하지 마십시오. 항목을 또는 종료를 master 구문 중 하나에 없는 묵시적된 장벽이 있습니다.