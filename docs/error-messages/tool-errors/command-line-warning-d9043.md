---
title: "명령줄 경고 D9043 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9043"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9043"
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 명령줄 경고 D9043
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'warning\_level' 값을 'compiler\_option'에 사용할 수 없습니다. '4999'\(으\)로 가정합니다. 코드 분석 경고가 경고 수준과 연결되어 있지 않습니다.  
  
## 예제  
 다음 샘플에서는 C9043 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// D9043.cpp  
// compile with: /analyze /w16001  
// D9043 warning expected  
int main() {}  
```