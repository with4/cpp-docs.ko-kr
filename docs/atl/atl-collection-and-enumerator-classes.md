---
title: ATL 컬렉션 및 열거자 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a47525bb21b896b0fef8393cab66142ed40311ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354448"
---
# <a name="atl-collection-and-enumerator-classes"></a>ATL 컬렉션 및 열거자 클래스
ATL은 컬렉션 및 열거자를 구현 하려면 다음 클래스를 제공 합니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|컬렉션 인터페이스 구현|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|열거자 인터페이스 구현 (c + + 표준 라이브러리 호환 컨테이너에 저장 된 데이터를 가정 합니다.)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|열거자 인터페이스 구현 (배열에 저장 된 데이터를 가정 합니다.)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|열거자 개체 구현 (사용 하 여 `IEnumOnSTLImpl`)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|열거자 개체 구현 (사용 하 여 `CComEnumImpl`)|  
|[_Copy](../atl/atl-copy-policy-classes.md)|정책 클래스를 복사 합니다.|  
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|정책 클래스를 복사 합니다.|  
|[CAdapt](../atl/reference/cadapt-class.md)|어댑터 클래스 (숨깁니다 **연산자 &** 허용 `CComPtr`, `CComQIPtr`, 및 `CComBSTR` c + + 표준 라이브러리 컨테이너에 저장 될)|  
  
## <a name="see-also"></a>참고 항목  
 [컬렉션 및 열거자](../atl/atl-collections-and-enumerators.md)

