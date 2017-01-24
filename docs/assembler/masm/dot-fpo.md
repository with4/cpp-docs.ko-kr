---
title: ".FPO | Microsoft Docs"
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
  - ".FPO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".FPO directive"
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .FPO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당 합니다.FPO 지시문 디버그 레코드.debug$ F 세그먼트 또는 섹션의 내보내기를 제어합니다.  
  
## 구문  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### 매개 변수  
 `cdwLocals`  
 로컬 변수를 부호 없는 32 비트 값의 수입니다.  
  
 `cdwParams`  
 DWORD 부호 없는 16 비트 값의 매개 변수 크기입니다.  
  
 *cbProlog*  
 함수 프롤로그 코드는 부호 없는 8 비트 값의 바이트 수입니다.  
  
 `cbRegs`  
 저장 된 레지스터 번호입니다.  
  
 `fUseBP`  
 EBP 레지스터 할당 되었는지 여부를 나타냅니다.  0 또는 1입니다.  
  
 *cbFrame*  
 프레임 유형을 나타냅니다.  자세한 내용은 [FPO\_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352)를 참조하십시오.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)