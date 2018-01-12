---
title: "심각한 오류 C1070 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1070
dev_langs: C++
helpviewer_keywords: C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c852b8c3d7e80fb58025f13a142d7c20dac6596
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1070"></a>심각한 오류 C1070
'filename' 파일에서 #if/#endif 쌍이 짝이 맞지 않습니다.  
  
 `#if`, `#ifdef`또는 `#ifndef` 지시문에 해당하는 `#endif`가 없습니다.  
  
 다음 샘플에서는 C1070을 생성합니다.  
  
```  
// C1070.cpp  
#define TEST  
  
#ifdef TEST  
  
#ifdef TEST  
#endif  
// C1070  
```  
  
 해결 방법:  
  
```  
// C1070b.cpp  
// compile with: /c  
#define TEST  
  
#ifdef TEST  
#endif  
  
#ifdef TEST  
#endif  
```