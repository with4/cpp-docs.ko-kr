---
title: "심각한 오류 C1021 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1021
dev_langs: C++
helpviewer_keywords: C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc291812a582332ec281a3bead2a9b0fede88869
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1021"></a>심각한 오류 C1021
'string' 전처리기 명령이 잘못되었습니다.  
  
 `string` 은 유효하지 않은 [전처리기 지시문](../../preprocessor/preprocessor-directives.md)입니다. 오류를 해결하려면 `string`에 대해 올바른 전처리기 이름을 사용합니다.  
  
 다음 샘플에서는 C1021을 생성합니다.  
  
```  
// C1021.cpp  
#BadPreProcName    // C1021 delete line  
```