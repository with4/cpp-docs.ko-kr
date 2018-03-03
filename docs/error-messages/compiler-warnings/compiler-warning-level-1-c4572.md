---
title: "컴파일러 경고 (수준 1) C4572 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4572
dev_langs:
- C++
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee599d1385d71fee1b03d4298f27e1c8ed5ccbd2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4572"></a>컴파일러 경고(수준 1) C4572
'...'를 사용, /clr [ParamArray] 특성은 사용 되지 않습니다. 대신  
  
 가변 인수 목록을 지정 하는 사용 되지 않는 스타일 사용 되었습니다. CLR을 컴파일할 때 대신 줄임표 구문을 사용 하 여 <xref:System.ParamArrayAttribute>합니다. 자세한 내용은 참조 [가변 인수 목록 (...) (C + + /CLI CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4572 경고가 발생 합니다.  
  
```  
// C4572.cpp  
// compile with: /clr /W1  
void Func([System::ParamArray] array<int> ^);   // C4572  
void Func2(... array<int> ^){}   // OK  
  
int main() {  
   Func2(1, 2, 3);  
}  
```