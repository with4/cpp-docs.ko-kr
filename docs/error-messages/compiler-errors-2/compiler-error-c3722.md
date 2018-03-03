---
title: "컴파일러 오류 C3722 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3722
dev_langs:
- C++
helpviewer_keywords:
- C3722
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88f3706c21de38669be007b5fe92248670086f71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3722"></a>컴파일러 오류 C3722
일반 이벤트 허용 되지 않습니다.  
  
 컴파일러는 제네릭 클래스, 구조체 및 함수에만 허용합니다.  자세한 내용은 [제네릭](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C3722 오류가 생성 됩니다.  
  
```  
// C3722.cpp  
// compile with: /clr  
generic <typename T>  
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);  
  
generic <class T>  
public ref struct MyButton {  
   generic<typename U>  
   event MyEventHandler<U>^ Click;   // C3722  
};  
```