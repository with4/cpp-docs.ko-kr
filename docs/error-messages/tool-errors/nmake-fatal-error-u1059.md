---
title: "NMAKE 심각한 오류 U1059 | Microsoft Docs"
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
  - "U1059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1059"
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 심각한 오류 U1059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류: 종속 파일에 '}'가 없습니다.  
  
 종속 파일의 검색 경로가 잘못 지정되었습니다.  경로에 공백이 있거나 닫는 중괄호\(**}**\)가 생략되었습니다.  
  
 종속 파일에 대한 디렉터리 사양의 구문은 다음과 같습니다.  
  
 **{**   
 ***directories* }dependent**  
  
 여기에 `directories`는 한 개 이상의 경로를 지정하며 각 경로는 세미콜론\(**;**\)으로 구분됩니다.  공백은 사용할 수 없습니다.  
  
 검색 경로의 일부 또는 전체가 매크로로 대체되면 매크로 확장에 공백이 없어야 합니다.