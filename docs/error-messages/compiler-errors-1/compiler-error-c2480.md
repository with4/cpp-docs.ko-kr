---
title: 컴파일러 오류 C2480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987cefa42b3f3f8d9588e446ca181c0b7cd48f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198588"
---
# <a name="compiler-error-c2480"></a>컴파일러 오류 C2480
'identifier': 't h'는 정적 범위의 데이터 항목에만 유효  
  
 사용할 수 없습니다는 `thread` 는 자동 변수, 비정적 데이터 멤버, 함수 매개 변수 또는 함수 선언 또는 정의에 특성입니다.  
  
 사용 하 여는 `thread` 전역 변수, 정적 데이터 멤버 및 지역 정적 변수에에 대 한 특성입니다.  
  
 다음 샘플에서는 C2480 오류가 생성 됩니다.  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```