---
title: 다중 인라인 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee9be15f029c0aaab3ca4bc47fb183e1499c2e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368215"
---
# <a name="multiple-inline-files"></a>인라인 파일이 여러 개인 경우
명령을 여러 개 인라인 파일을 만들 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>설명  
 각 파일에 대 한 하나 이상의 다음에 닫는 줄 구분 기호를 포함 하는 인라인 텍스트 줄을 지정 합니다. 첫 번째 파일에 대 한 구분 줄을 다음 줄에 두 번째 파일의 텍스트를 시작 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)