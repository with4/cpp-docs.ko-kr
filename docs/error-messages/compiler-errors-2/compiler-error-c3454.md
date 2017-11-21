---
title: "컴파일러 오류 C3454 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3454
dev_langs: C++
helpviewer_keywords: C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 026b77ca4f9488c1178a2815ffb0a9c7c71bdf54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3454"></a>컴파일러 오류 C3454
[attribute]는 클래스 선언에 사용할 수 없습니다.  
  
 클래스는 특성이 되도록 정의되어야 합니다.  
  
 자세한 내용은 [attribute](../../windows/attribute.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3454를 생성합니다.  
  
```  
// C3454.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute]   // C3454  
ref class Attr1;  
  
[attribute]   // OK  
ref class Attr2 {};  
```