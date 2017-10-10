---
title: "컴파일러 오류 C2696 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2696
dev_langs:
- C++
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 70ccaf34a0191f0bd69c95d2cb110f6e6542a6d1
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2696"></a>컴파일러 오류 C2696
관리 되는 형식 'type'의 임시 개체를 만들 수 없습니다.  
  
에 대 한 참조 `const` 관리 되지 않는 프로그램에서 사용 하면 컴파일러가 생성자를 호출 하 고 스택에 임시 개체를 만듭니다. 그러나 관리 되는 클래스를 스택에 되지 만들 수 있습니다.  
  
C2696은 사용 되지 않는 컴파일러 옵션을 사용 하 여 연결할 수만 **/clr:oldSyntax**합니다.  

