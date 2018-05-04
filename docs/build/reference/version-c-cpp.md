---
title: VERSION (C/C + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcaf4e113af6182a2d3d735e4c668b62336e2c79
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="version-cc"></a>VERSION(C/C++)
.Exe 파일의 헤더에 숫자를 저장 하는 링크 또는 DLL에 지시 합니다.  
  
```  
VERSION major[.minor]  
```  
  
## <a name="remarks"></a>설명  
 *주요* 및 *부* 인수는 0-65535 범위의 10 진수 숫자입니다. 기본값은 0.0 버전입니다.  
  
 버전 번호를 지정 하는 해당 하는 방법은 [버전 정보](../../build/reference/version-version-information.md) (/ 버전) 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)