---
title: "링커 도구 오류 LNK1107 | Microsoft Docs"
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
  - "LNK1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1107"
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일이 잘못되었거나 손상되었습니다. location에서 읽을 수 없습니다.  
  
 도구가 파일을 읽지 못했습니다.  파일을 다시 만드십시오.  
  
 모듈을 전달 하려는 경우에 LNK1107 발생할 수 \(.dll 또는.netmodule 확장명을 사용하여 만든 [\/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) 또는 [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)\)을. 대신.obj 파일을 전달 합니다.  
  
 다음 샘플을 컴파일한 다음  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 명령줄에 **link LNK1107.dll**을 지정하면 LNK1107 오류가 발생합니다.  이 오류를 해결하려면 대신 **link LNK1107.obj**를 지정하십시오.