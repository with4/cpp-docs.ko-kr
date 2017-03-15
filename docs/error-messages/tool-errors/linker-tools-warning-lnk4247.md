---
title: "링커 도구 경고 LNK4247 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4247"
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 링커 도구 경고 LNK4247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'decorated\_function\_name' 진입점에는 이미 스레드 특성이 있습니다. 'attribute'이\(가\) 무시되었습니다.  
  
 [\/ENTRY\(진입점 기호\)](../../build/reference/entry-entry-point-symbol.md)를 사용하여 지정한 진입점에 스레드 특성이 있지만 다른 스레드 모델을 사용하여 [\/CLRTHREADATTRIBUTE\(CLR 스레드 특성 설정\)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)도 지정했습니다.  
  
 링커는 \/CLRTHREADATTRIBUTE를 사용하여 지정한 값을 무시합니다.  
  
 이 경고를 해결하려면  
  
-   빌드에서 \/CLRTHREADATTRIBUTE를 제거합니다.  
  
-   소스 코드 파일에서 특성을 제거합니다.  
  
-   소스의 특성과 빌드의 \/CLRTHREADATTRIBUTE를 모두 제거하고 기본 CLR 스레드 모델을 적용합니다.  
  
-   소스의 특성과 일치하도록 전달된 값을 \/CLRTHREADATTRIBUTE로 변경합니다.  
  
-   \/CLRTHREADATTRIBUTE에 전달된 값과 일치하도록 소스의 특성을 변경합니다.  
  
 다음 샘플에서는 LNK4247 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```