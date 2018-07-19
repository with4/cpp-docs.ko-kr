---
title: -RAWDATA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rawdata
dev_langs:
- C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28691e636f01174ecfe2a9d48b016523fce67f14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375001"
---
# <a name="rawdata"></a>/RAWDATA
```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## <a name="remarks"></a>설명  
 이 옵션은 파일의 각 섹션의 원시 콘텐츠를 표시합니다. 아래와 같이 디스플레이의 서식을 제어 하는 인수:  
  
|인수|결과|  
|--------------|------------|  
|1|기본값입니다. 내용이 인쇄 가능할 경우 16 진수 바이트 및 ASCII 문자로 표시 됩니다.|  
|2|내용이 2 바이트의 16 진수 값으로 표시 됩니다.|  
|4|콘텐츠는 16 진수 4 바이트 값으로 표시 됩니다.|  
|8|콘텐츠는 16 진수 8 바이트 값으로 표시 됩니다.|  
|없음|원시 데이터는 표시 되지 않습니다. 이 인수는 출력을 제어 하는 데 유용/모든 합니다.|  
|*숫자*|표시 된 줄의 너비를 설정 `number` 줄 하나에 값이 있습니다.|  
  
 만 [/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은으로 생성 된 파일에서 사용 하기 위해 사용할 수는 [/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)