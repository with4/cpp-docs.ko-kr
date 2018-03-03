---
title: "컴파일러 경고 (수준 1) C4122 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4122
dev_langs:
- C++
helpviewer_keywords:
- C4122
ms.assetid: 9a83eb0d-8708-42f7-988a-b0b6f2f646a0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b78c0f3589d40f18e96f52e9bfb642c8550becb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4122"></a>컴파일러 경고(수준 1) C4122
'function': alloc_text는 C 링크가 있는 함수에만 적용될 수 있습니다.  
  
 **alloc_text** pragma는 **extern c**로 선언된 함수에만 적용됩니다. 외부 C++ 함수와 함께 사용할 수 없습니다.  
  
 pragma가 무시됩니다.