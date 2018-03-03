---
title: "2.6.6 ordered 구문 | Microsoft Docs"
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
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e09a9d756cd068df9345034e26a4f152d3ac19fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="266-ordered-construct"></a>2.6.6 ordered 구문
구조화 된 블록 다음은 **정렬** 지시문 반복 하면 순차 루프에 실행할 수 있는 순서 대로 실행 됩니다. 구문은 **정렬** 지시문은 다음과 같습니다.  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 **정렬** 지시문의 동적 범위 내에 있어야 합니다.는 **에 대 한** 또는 **에 대 한 병렬** 생성 합니다. **에 대 한** 또는 **에 대 한 병렬** 지시문에 **정렬** 구문 바인딩에 있어야는 **정렬** 에 설명 된 대로 지정 된 절 [섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지에 있습니다. 실행 중에 **에 대 한** 또는 **에 대 한 병렬** 를 생성는 **정렬** 절 **정렬** 구문에 엄격 하 게 실행 되는 실행할 수 있는 루프의 순차적 실행의 순서입니다.  
  
 에 대 한 제한 된 **정렬** 지시문은 다음과 같습니다.  
  
-   포함 하는 루프의 반복은 **에 대 한** 구문이 동일한 순서가 지정 된 지시문 두 번 이상 실행 해서는 안을 여러 개 실행 하지 해야 **정렬** 지시문입니다.