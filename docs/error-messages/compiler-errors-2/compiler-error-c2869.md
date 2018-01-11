---
title: "컴파일러 오류 C2869 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2869
dev_langs: C++
helpviewer_keywords: C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6780457258e8ebbf3b98b81ce419839e78fb2b40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2869"></a>컴파일러 오류 C2869
'name': 이미 네임 스페이스로 정의  
  
 네임 스페이스도 이미 사용 되는 이름을 다시 사용할 수 없습니다.  
  
 다음 샘플에서는 C2869 오류가 생성 됩니다.  
  
```  
// C2869.cpp  
// compile with: /c  
namespace A { int i; };  
  
class A {};   // C2869, A is already used  
```