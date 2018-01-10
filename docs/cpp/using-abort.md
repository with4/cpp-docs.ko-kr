---
title: "Abort 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Abort
dev_langs: C++
helpviewer_keywords: abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 88f7d2319fd238fbc7bf573d304245ca74696720
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-abort"></a>abort 사용
호출 된 [중단](../c-runtime-library/reference/abort.md) 함수 때문에 즉시 종료 합니다. 이 함수는 초기화된 전역 정적 개체에 대한 일반적인 소멸 프로세스를 건너뜁니다. 또한 이 함수는 `atexit` 함수를 사용하여 지정된 모든 특수 처리를 건너뜁니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)