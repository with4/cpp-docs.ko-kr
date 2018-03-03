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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4d6efbf8dcf10d1608bb1a54b843a49d42cb22a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2696"></a>컴파일러 오류 C2696
관리 되는 형식 'type'의 임시 개체를 만들 수 없습니다.  
  
에 대 한 참조 `const` 관리 되지 않는 프로그램에서 사용 하면 컴파일러가 생성자를 호출 하 고 스택에 임시 개체를 만듭니다. 그러나 관리 되는 클래스를 스택에 되지 만들 수 있습니다.  
  
C2696은 사용 되지 않는 컴파일러 옵션을 사용 하 여 연결할 수만 **/clr:oldSyntax**합니다.  
