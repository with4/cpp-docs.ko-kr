---
title: "컴파일러 경고 (수준 1) C4079 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4079"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4079"
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4079
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예기치 않은 'token' 토큰입니다.  
  
 pragma 인수 목록에서 예기치 않은 구분선 토큰이 발생하여  pragma의 나머지 부분이 무시되었습니다.  
  
 다음 샘플에서는 C4079 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```