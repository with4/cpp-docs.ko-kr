---
title: "형식 라이브러리 액세스 | Microsoft 문서"
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
- type libraries, accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8a3fbcf66036ef3df3bd34b5182dac8af3dfccef
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="type-library-access"></a>형식 라이브러리 액세스
형식 라이브러리는 다른 OLE 인식 응용 프로그램에는 OLE 컨트롤의 인터페이스를 노출합니다. 하나 이상의 인터페이스를 노출 하려는 경우 각 OLE 컨트롤에서 형식 라이브러리를 가져야 합니다.  
  
 다음 매크로 사용 하는 자체 형식 라이브러리에 대 한 액세스를 제공 하는 OLE 컨트롤:  
  
### <a name="type-library-access"></a>형식 라이브러리 액세스  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|선언 된 `GetTypeLib` (클래스 선언에 사용 해야 합니다) OLE 컨트롤의 멤버 함수입니다.|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|구현 하는 `GetTypeLib` (클래스 구현에 사용 해야 합니다) OLE 컨트롤의 멤버 함수입니다.|  
  
##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 선언 된 `GetTypeLib` 컨트롤 클래스의 멤버 함수입니다.  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 형식 라이브러리와 관련 된 컨트롤 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 클래스 헤더 파일에서이 매크로 사용 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 컨트롤의 구현 `GetTypeLib` 멤버 함수입니다.  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>매개 변수  
 *눈여겨 보십시오*  
 형식 라이브러리와 관련 된 컨트롤 클래스의 이름입니다.  
  
 *tlid*  
 형식 라이브러리의 ID.  
  
 `wVerMajor`  
 형식 라이브러리의 주 버전 번호입니다.  
  
 `wVerMinor`  
 형식 라이브러리의 부 버전 번호입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하는 컨트롤 클래스는 구현 파일에 표시 되어야는 `DECLARE_OLETYPELIB` 매크로입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
   
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

