---
title: "컴파일러 오류 C2833 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2833
dev_langs: C++
helpviewer_keywords: C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 019fa3cb0b36d9062bc972b01d434afe6e3848aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2833"></a>컴파일러 오류 C2833
'operator 연산자' 인식된 연산자 또는 형식이 아닙니다.  
  
 단어 `operator` 재정의 하려는 연산자나 변환 하려는 형식을 따라야 합니다.  
  
 관리 되는 형식에서 정의할 수 있는 연산자의 목록에 대 한 참조 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)합니다.  
  
 다음 샘플에서는 C2833 오류가 생성 됩니다.  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```