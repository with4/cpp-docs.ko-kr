---
title: 컴파일러 오류 C2750 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2750
dev_langs:
- C++
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06731b0b386b200b74697592137aac10a48a8e82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2750"></a>컴파일러 오류 C2750
'type': 참조 형식에 'n e w'를 사용할 수 없습니다 대신 'gcnew'를 사용 하 여  
  
 사용 해야 인스턴스가 가비지 수집 힙에 배치 시키는 CLR 형식의 인스턴스를 만들려면 [gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C2750 오류가 생성 됩니다.  
  
```  
// C2750.cpp  
// compile with: /clr  
ref struct Y1 {};  
  
int main() {  
   Y1 ^ x = new Y1;   // C2750  
  
   // try the following line instead  
   Y1 ^ x2 = gcnew Y1;  
}  
```