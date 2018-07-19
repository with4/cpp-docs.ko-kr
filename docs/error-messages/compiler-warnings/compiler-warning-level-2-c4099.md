---
title: 컴파일러 경고 (수준 2) C4099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afecb3fb2420d27bedf16c81894f224a1119a67b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33309470"
---
# <a name="compiler-warning-level-2-c4099"></a>컴파일러 경고 (수준 2) C4099
'identifier': 형식 이름 'objecttype1' 'objecttype2'를 사용 하 여 표시를 사용 하 여 우선 표시  
  
 구조로 선언 된 개체는 클래스로 정의 됩니다 또는 구조체를 클래스로 선언 된 개체 이루어집니다. 컴파일러는 정의에 지정 된 형식을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c4099 오류가 발생 합니다.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```