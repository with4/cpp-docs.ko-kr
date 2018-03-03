---
title: "링커 도구 오류 LNK2039 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 441765d85ce65a80102ed94b3f4394ae48c0e29f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2039"></a>링커 도구 오류 LNK2039
ref 클래스를 가져오는\<유형 >' another.obj에 정의 된; 중 하나 가져온 또는 정의 여야 합니다  
  
 Ref 클래스 ' <`type`>'를 지정 된.obj 파일에서 가져오지만 다른.obj 파일에 정의 되어 있습니다. 이 조건은 런타임 오류 또는 기타 예기치 않은 동작을 일으킬 수 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  다른 .obj 파일에 '`type`'을 정의해야 하는지 여부 및 .winmd 파일에서 가져와야 하는지 여부를 확인합니다.  
  
2.  정의 또는 가져오기를 제거합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [링커 도구 오류 LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)