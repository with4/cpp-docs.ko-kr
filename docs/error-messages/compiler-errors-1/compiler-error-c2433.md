---
title: "컴파일러 오류 C2433 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2433
dev_langs:
- C++
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 565c013f36cf8c9037c461e74c24cf18a21194f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2433"></a>컴파일러 오류 C2433
'identifier': 'modifier' 데이터 선언에 사용할 수 없습니다  
  
 `friend`, `virtual`, 및 `inline` 데이터 선언에 대 한 한정자를 사용할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2433 오류가 발생 합니다.  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```