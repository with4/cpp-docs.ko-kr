---
title: "컴파일러 오류 C2348 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2348
dev_langs: C++
helpviewer_keywords: C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2be3e9c8d83443355c3090dd3083f800ae55d76d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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