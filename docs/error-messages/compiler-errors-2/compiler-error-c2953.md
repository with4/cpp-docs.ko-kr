---
title: 컴파일러 오류 C2953 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2953
dev_langs:
- C++
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 403ebce4fdb8b3ff8cf014c27cfc6ec988a1a897
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245112"
---
# <a name="compiler-error-c2953"></a>컴파일러 오류 C2953
'identifier': 클래스 템플릿이 이미 정의되었습니다.  
  
 소스 파일을 확인하고 다른 정의에 대한 파일을 포함합니다.  
  
 다음 샘플에서는 C2953을 생성합니다.  
  
```  
// C2953.cpp  
// compile with: /c  
template <class T>  class A {};  
template <class T>  class A {};   // C2953  
template <class T>  class B {};   // OK  
```