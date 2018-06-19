---
title: 명령줄 경고 D9041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c22573d26e09e14789f4cbd64d68f4082125c2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298641"
---
# <a name="command-line-warning-d9041"></a>명령줄 경고 D9041
에 대 한 값이 잘못 되었습니다 'value' '/option'; ' 값 '; 추가 ' /analyze '에이 경고를 지정 하는 경우 명령줄 옵션  
  
 코드 분석 경고 번호가 추가 되었고는 **/wd**, **/we**, **/wo**, 또는 **/wl** 는 도지정하지않고명령줄옵션 **/analyze** 명령줄 옵션입니다. 추가 하거나이 오류를 해결 하려면는 **/analyze** 명령줄 옵션 또는 적절 한 잘못 된 경고 번호를 제거 **/w** 명령줄 옵션입니다.  
  
## <a name="example"></a>예제  
 다음 명령줄 예제에서는 경고 D9041 오류가 생성 됩니다.  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 경고를 해결 하려면 추가 **/analyze** 명령줄 옵션입니다. 경우 **/analyze** 은에서 잘못 된 경고 번호를 제거 하는 컴파일러의 버전에 지원 되지 않습니다는 **/wd** 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령줄 오류 D8000 D9999 통해](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)