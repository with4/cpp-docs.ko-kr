---
title: "CMutex 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex class
- synchronization classes, CMutex class
- synchronization objects, mutex
- mutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 159f2e02dfe44d74ebcaad687a23cef734b61fc9
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmutex-class"></a>CMutex 클래스
"뮤텍스" 나타냅니다-리소스에 한 스레드가 상호 배타적인 액세스 허용 하는 동기화 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|`CMutex` 개체를 생성합니다.|  
  
## <a name="remarks"></a>주의  
 뮤텍스는 한 번에 하나의 스레드만 데이터 나 일부 다른 제어 된 리소스를 수정할 수 있게 될 수 있는 경우에 유용 합니다. 예를 들어, 한 번에 한 스레드에서 허용 해야 하는 프로세스는 연결 된 목록의 노드를 추가 합니다. 사용 하 여 한 `CMutex` 만 한 번에 하나의 스레드만 목록에 액세스할 수 있는 연결된 리스트를 제어 하는 개체입니다.  
  
 사용 하는 `CMutex` 개체, 구성의 `CMutex` 필요할 때 개체입니다. 뮤텍스를 대기 하려는 이름을 지정 하 고 응용 프로그램에서 소유한 처음 해야 합니다. 그런 다음 생성자는 반환 될 때 뮤텍스를 액세스할 수 있습니다. 호출 [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) 후 제어 된 리소스에 액세스 합니다.  
  
 대체 방법을 사용 하 여 `CMutex` 개체 형식의 변수를 추가 하는 것 `CMutex` 제어 하려는 클래스를 데이터 멤버로 합니다. 제어 되는 개체의 생성 하는 동안의 생성자를 호출는 `CMutex` 뮤텍스 처음 소유 하 고, 뮤텍스 (프로세스 경계를 넘어 사용 됨) 하는 경우의 이름 및 보안 특성을 원하는 경우를 지정 하는 데이터 멤버입니다.  
  
 리소스에 액세스 하 여 제어 `CMutex` 이 방법으로 개체는 두 가지 형식의 변수를 먼저 만듭니다 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 종류나 [CMultiLock](../../mfc/reference/cmultilock-class.md) 리소스의 액세스 멤버 함수에 있습니다. 다음은 잠금 개체의 호출 `Lock` 멤버 함수 (예를 들어 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). 이 시점에서 스레드 중 하나는 리소스에 액세스 하기를 하는 리소스를 해제 및 액세스를 얻거나, 출시 될 리소스 및 리소스에 액세스 실패 하는 시간 초과 될 때까지 기다립니다. 어떤 경우 든 스레드로부터 안전한 방식으로 리소스에 액세스 합니다. 리소스를 해제 하려면 잠금 개체를 사용 하 여 `Unlock` 멤버 함수 (예를 들어 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), 또는 범위를 벗어날 수 있는 잠금 개체를 허용 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CMutex` 개체, 문서를 참조 하십시오. [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmt.h  
  
##  <a name="cmutex"></a>CMutex::CMutex  
 명명 되거나 명명 되지 않은에서는 `CMutex` 개체입니다.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bInitiallyOwn`  
 지정 하는 경우 스레드 만들기는 `CMutex` 개체는 뮤텍스로 제어 되는 리소스에 대 한 액세스를 처음에 있습니다.  
  
 `lpszName`  
 `CMutex` 개체의 이름입니다. 동일한 이름의 다른 뮤텍스 있으면 `lpszName` 프로세스 경계를 넘어 개체를 사용할 예정 이면 제공 해야 합니다. 경우 **NULL**, 뮤텍스 명명 됩니다. 이름이 일치 하는 기존 뮤텍스, 생성자는 새 빌드하여 `CMutex` 해당 이름의 뮤텍스를 참조 하는 개체입니다. 이름이 일치 뮤텍스 되지 않은 기존 동기화 개체를 생성 하지 못합니다.  
  
 `lpsaAttribute`  
 뮤텍스 개체에 대 한 보안 특성입니다. 에 대 한 전체 설명은이 구조를 참조 하십시오. [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 에 액세스 하거나 해제 하려면는 `CMutex` 개체를 만들기는 [CMultiLock](../../mfc/reference/cmultilock-class.md) 또는 [경우 CSingleLock](../../mfc/reference/csinglelock-class.md) 개체와 호출 해당 [잠금](../../mfc/reference/csinglelock-class.md#lock) 및 [잠금 해제](../../mfc/reference/csinglelock-class.md#unlock) 멤버 함수입니다. 하는 경우는 `CMutex` 개체를 독립 실행형으로 사용 되는 호출 하 고, 해당 `Unlock` 멤버 함수를 해제 합니다.  
  
> [!IMPORTANT]
>  만든 후의 `CMutex` 개체를 사용 하 여 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 뮤텍스가 이미 존재 하지 않으면 되도록 합니다. 뮤텍스가 예기치 않게 존재, 불량 프로세스 무단 점유 되 고 뮤텍스를 악의적으로 사용 하 여 시도 수를 나타낼 수 있습니다. 이 경우 권장 되는 보안에 민감한 절차를 처리 및 개체를 만들 오류가 발생 한 경우 처럼 계속입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSyncObject 클래스](../../mfc/reference/csyncobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




