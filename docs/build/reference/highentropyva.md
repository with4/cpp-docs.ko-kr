---
title: -HIGHENTROPYVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36ca3ea93f494587663d863b1dc4646750d38e82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="highentropyva"></a>/HIGHENTROPYVA
실행 가능 이미지가 높은 엔트로피 64비트 ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 지정합니다.  
  
```  
  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션은 64비트 주소를 사용하는 ASLR이 지원되는지 여부를 나타내기 위해 .dll 파일 또는 .exe 파일의 헤더를 수정합니다. 실행 파일과 해당 파일이 종속된 모든 모듈에 대해 이 옵션을 설정하면 64비트 ASLR을 지원하는 운영 체제가 64비트 가상 주소 공간에서 임의 주소를 사용하여 로그 시에 실행 가능 이미지의 세그먼트 기준 주소를 다시 지정할 수 있습니다. 이처럼 큰 주소 공간을 사용하는 경우 공격자가 특정 메모리 영역의 위치를 추측하기가 어려워집니다.  
  
 기본적으로 링커는 64비트 실행 가능 이미지에 대해 이 옵션을 설정합니다. 이 옵션을 설정 하는 [/DYNAMICBASE](../../build/reference/dynamicbase.md) 옵션 설정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [EDITBIN 옵션](../../build/reference/editbin-options.md)   
 [/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows ISV 소프트웨어 보안 방어](http://msdn.microsoft.com/library/bb430720.aspx)