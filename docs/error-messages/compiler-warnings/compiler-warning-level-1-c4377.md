---
title: 컴파일러 경고 (수준 1) C4377 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef049f85cd17bfeaba243b84da9fca93ae4036b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274783"
---
# <a name="compiler-warning-level-1-c4377"></a>컴파일러 경고(수준 1) C4377
네이티브 형식은 기본적으로 private입니다. -d1PrivateNativeTypes는 사용 되지 않습니다.  
  
 어셈블리의 네이티브 형식은 이전 릴리스에서 문서화 되지 않은, 내부 컴파일러 옵션 고, 기본적으로 public 인 (**/d1PrivateNativeTypes**) 비공개로 설정 하는 해당 하는 데 사용 되었습니다.  
  
 네이티브 모든 형식 및 CLR 어셈블리의 기본값은 하므로 **/d1PrivateNativeTypes** 더 이상 필요 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4377 오류가 발생 합니다.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```