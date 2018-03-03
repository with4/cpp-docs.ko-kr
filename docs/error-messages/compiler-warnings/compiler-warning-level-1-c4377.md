---
title: "컴파일러 경고 (수준 1) C4377 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2cf61aa35bcfc40a40febb9e066caba6decd682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4377"></a>컴파일러 경고(수준 1) C4377
네이티브 형식은 기본적으로 private입니다. -d1PrivateNativeTypes는 사용 되지 않습니다.  
  
 어셈블리의 네이티브 형식은 이전 릴리스에서 문서화 되지 않은, 내부 컴파일러 옵션 고, 기본적으로 public 인 (**/d1PrivateNativeTypes**) 비공개로 설정 하는 해당 하는 데 사용 되었습니다.  
  
 네이티브 모든 형식 및 CLR 어셈블리의 기본값은 하므로 **/d1PrivateNativeTypes** 더 이상 필요 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4377 오류가 발생 합니다.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```