---
title: "컴파일러 경고 (수준 1) C4079 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4079
dev_langs: C++
helpviewer_keywords: C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ead27a4a9cf2da2b97089cef207ccf518d268ff7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4079"></a>컴파일러 경고 (수준 1) C4079
예기치 않은 'token' 토큰입니다.  
  
 예기치 않은 구분 토큰 pragma 인수 목록에서 발생합니다. Pragma의 나머지 부분에서는 무시 되었습니다.  
  
 다음 샘플에서는 C4079 오류가 생성 됩니다.  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```