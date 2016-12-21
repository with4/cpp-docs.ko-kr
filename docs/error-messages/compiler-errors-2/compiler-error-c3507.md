---
title: "컴파일러 오류 C3507 | Microsoft Docs"
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
  - "C3507"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3507"
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3507
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ProgID는 39자가 넘는 문자 'id'을\(를\) 포함할 수 없고 '.' 이외의 문장 부호를 사용할 수 없으며 숫자로 시작할 수도 없습니다.  
  
 [progid](../../windows/progid.md) 특성에는 사용 가능한 값에 대한 제한이 있습니다.  
  
 다음 샘플에서는 C3507 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```