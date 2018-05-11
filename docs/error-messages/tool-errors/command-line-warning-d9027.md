---
title: 명령줄 경고 D9027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe2493290c4e4cc5b744136b8e7036c6559220a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9027"></a>명령줄 경고 D9027
소스 파일 '\<파일 이름 >' 무시  
  
 CL.exe 입력된 소스 파일을 무시 합니다.  
  
 이 경고는 /Fo 옵션과 /c 옵션을 사용 하 여 명령줄에서 출력 파일 이름 사이 공백을 원인일 수 있습니다. 예를 들어:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 /Fo 사이 공백이 있기 때문에 및 `output.obj`, CL.exe에서는 `output.obj` 입력된 파일의 이름으로 합니다. 이 문제를 해결 하려면 공간을 제거 합니다.  
  
```  
cl /c /Fooutput.obj input.c   
```