---
title: "컴파일러 오류 C2803 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2472c0e1182ad11f5ea95e3411649e6214b110ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2803"></a>컴파일러 오류 C2803
'operator 연산자' 클래스 형식의 정식 매개 변수가 하나 이상 있어야 합니다.  
  
 오버 로드 된 연산자에 클래스 형식의 매개 변수가 부족합니다.  
  
 포인터가 아닌 참조를 사용하여 참조별로 매개 변수를 적어도 하나 이상 전달하거나 값별로 하나 이상 전달하여 "a < b"를 작성할 수 있도록 해야 합니다. a와 b는 클래스 A 형식입니다.  
  
 매개 변수가 모두 포인터인 경우 포인터 주소 순수 하 게 비교 이며 사용자 정의 변환을 사용 하지 않습니다.  
  
 다음 샘플에서는 C2803 오류가 생성 됩니다.  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```