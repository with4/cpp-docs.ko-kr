---
title: "C 런타임 오류 R6025 | Microsoft Docs"
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
  - "R6025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6025"
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C 런타임 오류 R6025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

순수 가상 함수 호출입니다.  
  
 개체가 인스턴스화되지 않아서 순수 가상 함수 호출을 처리할 수 없습니다.  
  
 응용 프로그램에서 이 오류가 표시되는 경우 응용 프로그램에 대한 기술 지원을 요청하십시오.  
  
 이 오류는 추상 기본 클래스의 가상 함수를 포인터를 통해 호출했기 때문에 발생합니다. 이 포인터는 파생 클래스의 형식으로 캐스팅하여 만들었으나 실제로는 기본 클래스에 대한 포인터입니다.  기본 클래스를 생성하는 동안 **void\***를 만든 경우 **void\***를 클래스에 대한 포인터로 캐스팅하면 이 오류가 발생합니다.  
  
 자세한 내용은 [Microsoft 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=75220)를 참조하십시오.