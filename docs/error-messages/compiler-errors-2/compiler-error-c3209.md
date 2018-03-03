---
title: "컴파일러 오류 C3209 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3209
dev_langs:
- C++
helpviewer_keywords:
- C3209
ms.assetid: 1de44e39-69d1-4894-8f89-ff92136e8e5d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c3f7d60762afa32a6800c510aa84b20a95397c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3209"></a>컴파일러 오류 C3209
'class': 제네릭 클래스 또는 관리 되는 WinRTclass 있어야 합니다.  
  
 제네릭 클래스는 관리되는 클래스 또는 Windows 런타임 클래스여야 합니다.  
  
 다음 샘플에서는 C3209를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3209.cpp  
// compile with: /clr  
generic <class T>  
class C {};   // C3209  
  
// OK - ref class can be generic  
generic <class T>  
ref class D {};  
```