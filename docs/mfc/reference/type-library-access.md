---
title: "형식 라이브러리 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 8f05738c02fd70fde5fc2d92c5ee1e823747797c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="type-library-access"></a>형식 라이브러리 액세스
형식 라이브러리는 다른 OLE 인식 응용 프로그램에 있는 OLE 컨트롤의 인터페이스를 노출합니다. 하나 이상의 인터페이스를 노출 해야 하는 경우 각 OLE 컨트롤 형식 라이브러리를 가져야 합니다.  
  
 다음 매크로 사용 하는 자체 형식 라이브러리에 대 한 액세스를 제공 하는 OLE 컨트롤:  
  
### <a name="type-library-access"></a>형식 라이브러리 액세스  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|선언 된 `GetTypeLib` (클래스 선언에 사용 해야 합니다) OLE 컨트롤의 멤버 함수입니다.|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|구현 된 `GetTypeLib` (클래스 구현에 사용 해야 합니다) OLE 컨트롤의 멤버 함수입니다.|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 선언 된 `GetTypeLib` 컨트롤 클래스의 멤버 함수입니다.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 형식 라이브러리와 관련 된 컨트롤 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 컨트롤 클래스 헤더 파일에서이 매크로 사용 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 컨트롤의 구현 `GetTypeLib` 멤버 함수입니다.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>매개 변수  
 *class_name*  
 형식 라이브러리와 관련 된 컨트롤 클래스의 이름입니다.  
  
 *tlid*  
 형식 라이브러리의 ID.  
  
 `wVerMajor`  
 형식 라이브러리 주 버전 번호입니다.  
  
 `wVerMinor`  
 형식 라이브러리 부 버전 번호입니다.  
  
### <a name="remarks"></a>설명  
 이 매크로 사용 하는 모든 컨트롤 클래스에 대 한 구현 파일에 나타나야 합니다는 `DECLARE_OLETYPELIB` 매크로입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
   
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

