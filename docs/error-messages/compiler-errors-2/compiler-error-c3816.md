---
title: "컴파일러 오류 C3816 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3816
dev_langs: C++
helpviewer_keywords: C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 866a12639507488d8b9c34ab13ea72cf2239b5fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3816"></a>컴파일러 오류 C3816
'declaration' 이전에 선언 되었거나 다른 관리 되는 또는 WinRTmodifier로 정의  
  
 정방향 선언 및 실제 선언에서는 특성의 선언에 충돌이나 불일치가 없어야 합니다.  
  
 다음 샘플에서는 C3816을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3816a.cpp  
// compile with: /clr /c  
class C1;  
// try the following line instead  
// ref class C1;  
  
ref class C1{  // C3816, forward declaration does not use ref  
};  
```