---
title: ".SAFESEH | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".SAFESEH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registering functions as exception handlers"
  - "SAFESEH directive"
  - ".SAFESEH directive"
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAFESEH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

함수를 구조적된 예외 처리기로 등록합니다.  
  
## 구문  
  
```  
  
.SAFESEH identifier  
```  
  
## 설명  
 *식별자* ID에 대해 로컬로 정의 된 해야 합니다  [PROC](../../assembler/masm/proc.md) 또는  [EXTRN](../../assembler/masm/extrn.md) PROC.  A  [레이블](../../assembler/masm/label-masm.md) 허용 되지 않습니다.  해당 합니다.SAFESEH 지시문이 필요는  [\/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe 명령줄 옵션입니다.  
  
 구조적된 예외 처리기에 대 한 자세한 내용은  [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 예를 들어, 안전한 예외 처리기를 등록 합니다 \(같이\) 새 masm에서는 파일 만들기, \/safeseh를 조합 하 고 연결 된 개체에 추가.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)