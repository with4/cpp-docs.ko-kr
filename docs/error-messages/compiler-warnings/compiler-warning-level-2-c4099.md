---
title: "컴파일러 경고 (수준 2) C4099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4099
dev_langs: C++
helpviewer_keywords: C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1eb64e859ef40397edeb872cc7f6f228f7ae89e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4099"></a>컴파일러 경고 (수준 2) C4099
'identifier': 형식 이름 'objecttype1' 'objecttype2'를 사용 하 여 표시를 사용 하 여 우선 표시  
  
 구조로 선언 된 개체는 클래스로 정의 됩니다 또는 구조체를 클래스로 선언 된 개체 이루어집니다. 컴파일러는 정의에 지정 된 형식을 사용 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 c4099 오류가 발생 합니다.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```