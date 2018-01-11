---
title: "링커 도구 경고 LNK4247 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4247
dev_langs: C++
helpviewer_keywords: LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 517605993199942f863faa78e14a022529214a64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4247"></a>링커 도구 경고 LNK4247
항목 지점 'decorated_function_name'에 이미 스레드 특성이 있습니다. ' attribute' 무시  
  
 지정 된 진입점 [/ENTRY (진입점 기호)](../../build/reference/entry-entry-point-symbol.md)에 스레드 특성이 있지만 [/CLRTHREADATTRIBUTE (CLR 스레드 특성 설정)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) 다른 스레딩 모델로 지정 되었습니다.  
  
 링커는 /CLRTHREADATTRIBUTE를 지정 된 값이 무시 됩니다.  
  
 이 경고를 해결 방법:  
  
-   빌드에서 /CLRTHREADATTRIBUTE를 제거 합니다.  
  
-   소스 코드 파일에서 특성을 제거 합니다.  
  
-   빌드, 소스 및 /CLRTHREADATTRIBUTE에서 두 특성을 제거 하 고 기본 CLR 스레딩 모델을 적용 합니다.  
  
-   소스에서 특성을 사용 해도 되도록 /CLRTHREADATTRIBUTE, 전달 되는 값을 변경 합니다.  
  
-   /CLRTHREADATTRIBUTE 전달 되는 값을 사용 해도 되도록 소스에 특성을 변경 합니다.  
  
 다음 샘플에서는 LNK4247  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```