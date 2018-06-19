---
title: 컴파일러 오류 C2348 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2348
dev_langs:
- C++
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9728b044d05374e46b685df385409ddc3cb614f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222243"
---
# <a name="compiler-error-c2348"></a>컴파일러 오류 C2348
'type name': 포함 IDL에서 내보낼 수 없습니다, C 스타일 집합체가 아닙니다.  
  
 배치 하는 `struct` 인.idl 파일에는 [내보내기](../../windows/export.md) 특성의 `struct` 만 데이터를 포함 해야 합니다.  
  
 다음 샘플에서는 C2348 오류가 생성 됩니다.  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```