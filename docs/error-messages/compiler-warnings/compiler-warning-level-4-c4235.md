---
title: "컴파일러 경고 (수준 4) C4235 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0fea028932a48b9c7ee1a677a3e6dc8078edc35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4235"></a>컴파일러 경고(수준 4) C4235
비표준 확장이 사용 됨: 'keyword' 키워드는이 아키텍처에서 지원 되지 않습니다  
  
 컴파일러는 사용한 키워드를 지원 하지 않습니다.  
  
 이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다. 예를 들어 c4235 수준 2 경고에, 다음 코드 줄을 사용 하 여  
  
```  
#pragma warning(2:4235)  
```  
  
 소스 코드 파일.