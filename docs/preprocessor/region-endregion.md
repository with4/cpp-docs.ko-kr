---
title: "지역, endregion | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs: C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad2eb3d094447ae3ae35b0dbe9dc0fef2fe06710
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="region-endregion"></a>region, endregion
**#pragma 지역** 확장 하거나 사용 하는 경우를 축소할 수 있는 코드 블록을 지정할 수 있습니다는 [개요 기능](/visualstudio/ide/outlining) Visual Studio 코드 편집기의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### <a name="parameters"></a>매개 변수  
 `comment`(선택 사항)  
 코드 편집기에 표시될 주석입니다.  
  
 *이름*(선택 사항)  
 영역의 이름입니다.  이 이름은 코드 편집기에 표시됩니다.  
  
## <a name="remarks"></a>설명  
 **#pragma endregion** 의 끝을 표시 한 **#pragma 지역** 블록입니다.  
  
 A `#region` 블록으로 종결 되어야 합니다 **#pragma endregion**합니다.  
  
## <a name="example"></a>예  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)