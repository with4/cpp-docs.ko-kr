---
title: "리소스 컴파일러 경고 RW4004 | Microsoft Docs"
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
  - "RW4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW4004"
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 리소스 컴파일러 경고 RW4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ASCII 문자가 가상 키 코드와 동일하지 않습니다.  
  
 VIRTKEY 형식 액셀러레이터 키의 가상 키 코드에 문자열 리터럴이 사용되었습니다.  
  
 이 경고가 발생할 경우에도 계속 작업을 진행할 수 있지만 생성된 액셀러레이터 키가 지정한 문자열과 일치하지 않을 수 있습니다.  VIRTKEY는 ASCII 액셀러레이터 키와 다른 키 코드를 사용합니다.  
  
 구문적으로 보면 문자열 리터럴은 올바르지만 WINDOWS.h의 **VK\_\* \#define** 값을 사용해야만 원하는 액셀러레이터 키를 가져올 수 있습니다.