---
title: "호출 예제 결과 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예제[C++], 호출 결과"
  - "결과, __cdecl 호출"
  - "결과, __fastcall 키워드 호출"
  - "결과, __stdcall 호출"
  - "결과, thiscall 호출"
ms.assetid: aa70a7cb-ba1d-4aa6-bd0a-ba783da2e642
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 호출 예제 결과
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
  
## \_\_cdecl  
 C 데코레이팅된 함수 이름은 "\_MyFunc"입니다.  
  
 ![CDECL 호출 규칙](../cpp/media/vc37i01.png "vc37I01")  
\_\_cdecl 호출 규칙  
  
## \_\_stdcall 및 thiscall  
 C 데코레이팅된 이름\(`__stdcall`\)은 "\_MyFunc@20."입니다. C 데코레이팅된 이름은 독점적입니다.  
  
 ![&#95;&#95;stdcall 및 thiscall 호출 규칙](../cpp/media/vc37i02.png "vc37I02")  
\_\_stdcall 및 thiscall 호출 규칙  
  
## \_\_fastcall  
 C 데코레이팅된 이름\(`__fastcall`\)은 "@MyFunc@20."입니다. C 데코레이팅된 이름은 독점적입니다.  
  
 ![&#95;&#95;fastcall 호출 규칙](../cpp/media/vc37i03.png "vc37I03")  
\_\_fastcall 호출 규칙  
  
### Microsoft 전용 종료  
  
## 참고 항목  
 [호출 예제: 함수 프로토타입 및 호출](../cpp/calling-example-function-prototype-and-call.md)