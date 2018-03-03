---
title: "컴파일러 오류 C3622 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75d853b01f4f88fbf5e435b3b1f7a86fed0c8388
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3622"></a>컴파일러 오류 C3622
'class': 'keyword' 인스턴스화할 수 없습니다 클래스 선언  
  
로 표시 된 클래스를 인스턴스화하려고 했습니다 [추상](../../windows/abstract-cpp-component-extensions.md)합니다. 로 표시 된 클래스가 `abstract` 기본 클래스로 사용할 수 있지만 인스턴스화할 수 없습니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C3622 오류가 발생 합니다.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
