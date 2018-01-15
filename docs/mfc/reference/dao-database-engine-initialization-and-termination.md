---
title: "DAO 데이터베이스 엔진 초기화 및 종료 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.data
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32dbcb02615f552a2bb26ec047b0b817bb828a95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO 데이터베이스 엔진 초기화 및 종료
DAO 데이터베이스 엔진은 먼저 해야 MFC DAO 개체를 사용할 때 초기화 하 고 종료 한 다음 응용 프로그램 또는 DLL 종료 되기 전에 합니다. 두 함수 `AfxDaoInit` 및 `AfxDaoTerm`, 이러한 작업을 수행 합니다.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>DAO 데이터베이스 엔진 초기화 및 종료  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|DAO 데이터베이스 엔진을 초기화합니다.|  
|[AfxDaoTerm](#afxdaoterm)|DAO 데이터베이스 엔진을 종료합니다.|  
  
##  <a name="afxdaoinit"></a>AfxDaoInit  
 이 함수를 DAO 데이터베이스 엔진을 초기화합니다.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>설명  
 대부분의 경우에서 호출할 필요가 없습니다 `AfxDaoInit` 호출 하기 때문에 응용 프로그램이 자동으로 필요 합니다.  
  
 호출에 대 한 예제 및 관련된 정보에 대 한 `AfxDaoInit`, 참조 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="afxdaoterm"></a>AfxDaoTerm  
 이 함수는 DAO 데이터베이스 엔진을 종료합니다.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>설명  
 일반 MFC DLL;에서이 함수를 호출 하려면만 하면 일반적으로, 응용 프로그램에서는 자동으로 호출 `AfxDaoTerm` 필요할 때.  
  
 기본 MFC Dll에서 호출 `AfxDaoTerm` 하기 전에 `ExitInstance` 함수, MFC DAO 개체를 모두 제거 된 후에 있습니다.  
  
 관련된 정보를 참조 하십시오. [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
