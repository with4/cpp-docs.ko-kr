---
title: "명령줄 경고 D9041 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 307d290bb525ee879f29853c6823d5b9565aba4b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9041"></a>명령줄 경고 D9041
에 대 한 값이 잘못 되었습니다 'value' '/option'; ' 값 '; 추가 ' /analyze '에이 경고를 지정 하는 경우 명령줄 옵션  
  
 코드 분석 경고 번호가 추가 되었고는 **/wd**, **/we**, **/wo**, 또는 **/wl** 는 도지정하지않고명령줄옵션**/analyze** 명령줄 옵션입니다. 추가 하거나이 오류를 해결 하려면는 **/analyze** 명령줄 옵션 또는 적절 한 잘못 된 경고 번호를 제거 **/w** 명령줄 옵션입니다.  
  
## <a name="example"></a>예  
 다음 명령줄 예제에서는 경고 D9041 오류가 생성 됩니다.  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 경고를 해결 하려면 추가 **/analyze** 명령줄 옵션입니다. 경우 **/analyze** 은에서 잘못 된 경고 번호를 제거 하는 컴파일러의 버전에 지원 되지 않습니다는 **/wd** 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령줄 오류 D8000 D9999 통해](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)