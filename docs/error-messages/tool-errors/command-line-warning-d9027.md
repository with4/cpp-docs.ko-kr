---
title: "명령줄 경고 D9027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2769eb5f78cb1d5bdd6749e65429d83b69a2807b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9027"></a>명령줄 경고 D9027
소스 파일 '\<파일 이름 >' 무시  
  
 CL.exe 입력된 소스 파일을 무시 합니다.  
  
 이 경고는 /Fo 옵션과 /c 옵션을 사용 하 여 명령줄에서 출력 파일 이름 사이 공백을 원인일 수 있습니다. 예:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 /Fo 사이 공백이 있기 때문에 및 `output.obj`, CL.exe에서는 `output.obj` 입력된 파일의 이름으로 합니다. 이 문제를 해결 하려면 공간을 제거 합니다.  
  
```  
cl /c /Fooutput.obj input.c   
```