---
title: "컴파일러 오류 C3297 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3297
dev_langs:
- C++
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 718a86ec9acf71f66b092060b6032bd4ec94cfa9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3297"></a>컴파일러 오류 C3297
'constraint_2': 'constraint_1'에 값 제약 조건이 있으므로 'constraint_1'을 제약 조건으로 사용할 수 없습니다.  
  
 값 클래스가 봉인되어 있습니다. 제약 조건이 값 클래스인 경우 다른 제약 조건이 파생될 수 없습니다.  
  
 자세한 내용은 참조 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + /cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3297을 생성합니다.  
  
```  
// C3297.cpp  
// compile with: /clr /c  
generic<class T, class U>  
where T : value class  
where U : T   // C3297  
public ref struct R {};  
```