---
title: "시스템 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3e2c41ec95b0e26276df4f9f42d2ac46de54975
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="system-function"></a>시스템 함수
**ANSI 4.10.4.5** **시스템** 함수에 의한 문자열의 실행 모드 및 내용  
  
 **시스템** 함수는 명령줄이 아닌 C 프로그램 내에서 내부 운영 체제 명령 또는 .EXE, .COM(Windows NT에서는 .CMD) 또는 .BAT 파일을 실행합니다.  
  
 시스템 함수는 명령 해석기를 찾습니다. 일반적으로 명령 해석기는 Windows NT 운영 체제에서 CMD.EXE, Windows에서는 COMMAND.COM을 찾습니다.  그런 다음 시스템 함수는 인수 문자열을 명령 해석기에 전달합니다.  
  
 자세한 내용은 [system, _wsystem](../c-runtime-library/reference/system-wsystem.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)