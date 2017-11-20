---
title: stdin, stdout, stderr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdin
- stderr
- stdout
dev_langs: C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8350cb0cea07298eefb9b3aa54b69a5b9d786d88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="stdin-stdout-stderr"></a>stdin, stdout, stderr
## <a name="syntax"></a>구문  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## <a name="remarks"></a>설명  
 입력, 출력 및 오류 출력에 대한 표준 스트림입니다.  
  
 기본적으로 표준 입력은 키보드에서 읽고 표준 출력 및 표준 오류는 화면에 출력됩니다.  
  
 다음 스트림 포인터를 표준 스트림에 액세스하는 데 사용할 수 있습니다.  
  
|포인터|스트림|  
|-------------|------------|  
|`stdin`|표준 입력|  
|**stdout**|표준 출력|  
|`stderr`|표준 오류|  
  
 이러한 포인터는 함수에 대한 인수로 사용할 수 있습니다. **getchar** 및 `putchar`와 같은 일부 함수는 자동으로 `stdin` 및 **stdout**을 사용합니다.  
  
 이러한 포인터는 상수입니다. 여기에 새로운 값을 할당할 수 없습니다. `freopen` 함수는 스트림을 디스크 파일 또는 다른 장치로 리디렉션하는 데 사용할 수 있습니다. 운영 체제에서는 명령 수준에서 프로그램의 표준 입력 및 출력을 리디렉션할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../c-runtime-library/stream-i-o.md)   
 [전역 상수](../c-runtime-library/global-constants.md)