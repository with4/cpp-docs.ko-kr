---
title: "IDispatch 및 IErrorInfo 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs: C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f39db3e844df884e8e95352bed2a078b01beede8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch 및 IErrorInfo를 지원합니다.
템플릿 클래스를 사용할 수 있습니다 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 하는 `IDispatch Interface` 개체에는 이중 인터페이스의 부분입니다.  
  
 개체가 사용 하는 경우는 `IErrorInfo` 오류를 다시 클라이언트에 사용자 개체가 지원 해야 하며 보고서에 대 한 인터페이스는 `ISupportErrorInfo Interface` 인터페이스입니다. 템플릿 클래스 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 개체에서 오류를 생성 하는 단일 인터페이스 하나만 있는 경우이 구현 하는 쉬운 방법을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)

