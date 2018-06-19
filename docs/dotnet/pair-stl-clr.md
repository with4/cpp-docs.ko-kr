---
title: pair (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::pair
dev_langs:
- C++
helpviewer_keywords:
- pair class [STL/CLR]
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2d05dceaa763f8d0e33ccc86e783f66447c48b76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33160825"
---
# <a name="pair-stlclr"></a>pair(STL/CLR)
템플릿 클래스는 값의 쌍을 래핑하는 개체를 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>매개 변수  
 값 1  
 첫 번째 래핑된 값의 형식입니다.  
  
 Value2  
 두 번째 래핑된 값의 형식입니다.  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[pair::first_type(STL/CLR)](../dotnet/pair-first-type-stl-clr.md)|첫 번째 래핑된 값의 형식입니다.|  
|[pair::second_type(STL/CLR)](../dotnet/pair-second-type-stl-clr.md)|두 번째 래핑된 값의 형식입니다.|  
  
|멤버 개체|설명|  
|-------------------|-----------------|  
|[pair::first(STL/CLR)](../dotnet/pair-first-stl-clr.md)|첫 번째 값을 저장 합니다.|  
|[pair::second(STL/CLR)](../dotnet/pair-second-stl-clr.md)|두 번째 저장 된 값입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[pair::pair(STL/CLR)](../dotnet/pair-pair-stl-clr.md)|쌍 개체를 만듭니다.|  
|[pair::swap(STL/CLR)](../dotnet/pair-swap-stl-clr.md)|두 쌍의 내용을 바꿉니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[pair::operator=(STL/CLR)](../dotnet/pair-operator-assign-stl-clr.md)|저장 된 값 쌍을을 바꿉니다.|  
  
## <a name="remarks"></a>설명  
 개체는 한 쌍의 값을 저장합니다. 이 템플릿 클래스를 사용 하 여 두 값을 단일 개체로 결합 합니다. `cliext::pair` (여기에서 설명) 형식에만 관리 되는 저장소; 형식을 사용 하 여 관리 되지 않는 쌍을 저장 하 `std::pair`에 선언 된 `<utility>`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [make_pair(STL/CLR)](../dotnet/make-pair-stl-clr.md)