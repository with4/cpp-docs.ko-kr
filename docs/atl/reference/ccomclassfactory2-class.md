---
title: "CComClassFactory2 Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComClassFactory2<license>"
  - "CComClassFactory2"
  - "ATL.CComClassFactory2<license>"
  - "ATL::CComClassFactory2"
  - "ATL.CComClassFactory2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory2 class"
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactory2 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 구현 된  [에서는 IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) 인터페이스.  
  
## 구문  
  
```  
  
      template <  
   class license  
>  
class CComClassFactory2 : public IClassFactory2,  
   public CComObjectRootEx<CComGlobalsThreadModel>,  
   public license  
```  
  
#### 매개 변수  
 *라이센스*  
 다음 정적 함수를 구현 하는 클래스.  
  
-   **정적 BOOL VerifyLicenseKey \(BSTR** `bstr` **\);**  
  
-   **static BOOL GetLicenseKey\( DWORD**  `dwReserved` **, BSTR\***  `pBstr`  **\);**  
  
-   **정적 BOOL IsLicenseValid \(\);**  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CComClassFactory2::CreateInstance](../Topic/CComClassFactory2::CreateInstance.md)|지정한 CLSID의 개체를 만듭니다.|  
|[CComClassFactory2::CreateInstanceLic](../Topic/CComClassFactory2::CreateInstanceLic.md)|지정 된 라이센스 키를 지정 된 CLSID의 개체를 만듭니다.|  
|[CComClassFactory2::GetLicInfo](../Topic/CComClassFactory2::GetLicInfo.md)|클래스 팩터리를 라이센스 기능을 설명 하는 정보를 검색 합니다.|  
|[CComClassFactory2::LockServer](../Topic/CComClassFactory2::LockServer.md)|메모리에서 클래스 팩터리를 잠급니다.|  
|[CComClassFactory2::RequestLicKey](../Topic/CComClassFactory2::RequestLicKey.md)|만들고 라이센스 키를 반환 합니다.|  
  
## 설명  
 `CComClassFactory2`구현 된  [에서는 IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) 은 인터페이스의  [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364).  **에서는 IClassFactory2** 컨트롤 개체는 라이센스를 생성 합니다.  클래스 팩터리 사용이 허가 된 컴퓨터에서 실행 런타임 라이센스 키를 제공할 수 있습니다.  이 라이센스 키 전체 컴퓨터 라이센스 없을 때 개체를 인스턴스화할 수 있습니다.  
  
 ATL 개체 정상적으로 취득 팩터리 클래스에서 파생 하 여  [CComCoClass](../../atl/reference/ccomcoclass-class.md).  이 클래스는 매크로 포함  [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md)는 선언  [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로.  사용할 `CComClassFactory2`, 지정 된  [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) 매크로 개체의 클래스 정의에.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/CPP/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, 템플릿 매개 변수를 `CComClassFactory2`, 정적 함수를 구현 해야 `VerifyLicenseKey`, `GetLicenseKey`, 및 `IsLicenseValid`.  다음은 간단한 라이센스 클래스의 예제입니다.  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/CPP/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2`둘 다에서 파생 된  **CComClassFactory2Base** 및  *라이센스*.  **CComClassFactory2Base**, 따라서 파생  **에서는 IClassFactory2** 및  **CComObjectRootEx \< CComGlobalsThreadModel \>**.  
  
## 상속 계층 구조  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComClassFactoryAutoThread Class](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)