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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7d569243a6d0d1669a8964ab9c419cb0e7428ba9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="command-line-warning-d9027"></a>명령줄 경고 D9027
소스 파일 '\<파일 이름 > ' 무시  
  
 CL.exe 입력된 소스 파일을 무시 합니다.  
  
 이 경고는 /Fo 옵션과 /c 옵션을 사용 하 여 명령줄에서 출력 파일 이름 사이 공백을 원인일 수 있습니다. 예:  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 /Fo 사이 공백이 있기 때문에 및 `output.obj`, CL.exe에서는 `output.obj` 입력된 파일의 이름으로 합니다. 이 문제를 해결 하려면 공간을 제거 합니다.  
  
```  
cl /c /Fooutput.obj input.c   
```
