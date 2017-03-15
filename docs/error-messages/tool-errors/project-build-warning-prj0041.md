---
title: "프로젝트 빌드 경고 PRJ0041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0041"
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 프로젝트 빌드 경고 PRJ0041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'dependency' 종속성\(대상 파일: 'file'\)을 찾을 수 없습니다.이 경우 프로젝트를 빌드할 수는 있지만 이 파일이 없으면 계속 이전 버전으로 표시됩니다.  
  
 리소스 파일이나 .idl\/.odl 파일 등에 프로젝트 시스템에서 확인할 수 없는 include 문이 들어 있습니다.  
  
 프로젝트 시스템에서 \#if와 같은 전처리기 문을 처리하지 않으므로 잘못된 문이 실질적으로는 빌드에 포함되지 않을 수 있습니다.  
  
 이 경고를 해결하려면 .rc 파일에서 필요하지 않은 코드를 모두 삭제하거나 적절한 이름의 자리 표시자 파일을 추가하십시오.