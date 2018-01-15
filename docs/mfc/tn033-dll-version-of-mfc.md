---
title: "TN033: MFC의 DLL 버전 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.dll
dev_langs: C++
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba51ca465bec2a6400106071fcba94d36ad100e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn033-dll-version-of-mfc"></a>TN033: MFC의 DLL 버전
이 노트 방법을 MFCxx.DLL를 사용할 수 있습니다 및 MFCxxD.DLL (여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리 MFC 응용 프로그램 및 MFC 확장 Dll 설명 합니다. 일반 MFC Dll에 대 한 자세한 내용은 참조 [DLL의 일부로 MFC 사용 하 여](../mfc/tn011-using-mfc-as-part-of-a-dll.md)합니다.  
  
 이 기술 노트에서는 Dll의 세 가지 측면을 설명합니다. 마지막 두 고급 사용자를 위한 형식은:  
  
- [MFC 확장 DLL을 구축 하는 방법](#_mfcnotes_how_to_write_an_mfc_extension_dll)  
  
- [MFC의 DLL 버전을 사용 하는 MFC 응용 프로그램을 구축 하는 방법](#_mfcnotes_writing_an_application_that_uses_the_dll_version)  
  
- [구현 되는 MFC 동적 연결 라이브러리를 공유 하는 방법](#_mfcnotes_how_the_mfc30.dll_is_implemented)  
  
 비 MFC 응용 프로그램 (이 기본 MFC DLL)에 사용할 수 있는 MFC를 사용 하 여 DLL을 작성 하려는 경우 참조 [기술 참고 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)합니다.  
  
## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL 지원의 개요: 용어 및 파일  
 **일반 MFC DLL**: MFC 클래스 중 일부를 사용 하 여 dll을 독립 실행형 기본 MFC DLL을 사용 합니다. 응용 프로그램/DLL 경계를 넘어선 인터페이스는 "C" 인터페이스 및 클라이언트 응용 프로그램에서 MFC 응용 프로그램을 사용할 필요가 없습니다.  
  
 MFC 1.0에서 지원 되는 DLL 지원 버전입니다. 에 설명 되어 [기술 참고 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) 및 MFC 고급 개념 샘플 [DLLScreenCap](../visual-cpp-samples.md)합니다.  
  
> [!NOTE]
>  Visual c + + 버전 4.0부터 용어 **USRDLL** 사용 되지 않으며 정적으로 MFC에 링크 하는 MFC 기본 DLL로 대체 되었습니다. 일반 동적으로 MFC에 링크는 MFC DLL을 빌드할 수 있습니다.  
  
 MFC 3.0 이상 기본 MFC Dll OLE 및 데이터베이스 클래스를 포함 한 모든 새 기능을 지원 합니다.  
  
 **AFXDLL**: 이것은 라고도 MFC 라이브러리의 공유 버전입니다. 이 MFC 2.0에 추가 된 새 DLL 지원 합니다. MFC 라이브러리 자체 여러 Dll (아래 설명 참조)에 있으며 클라이언트 응용 프로그램 또는 DLL 필요한 Dll을 동적으로 링크 됩니다. 응용 프로그램/DLL 경계를 넘어 인터페이스는 C + + /cli MFC 클래스 인터페이스입니다. 클라이언트 응용 프로그램에는 MFC 응용 프로그램 이어야 합니다. 이 모든 MFC 3.0 기능을 지원 (예외: 데이터베이스 클래스에 대 한 유니코드를 사용할 수 없습니다).  
  
> [!NOTE]
>  Visual c + + 버전 4.0부터 이러한 종류의 DLL 라고 "확장 DLL입니다."  
  
 이 노트를 포함 하는 전체 MFC DLL 집합을 가리키는 MFCxx.DLL를 사용 합니다.  
  
-   디버그: MFCxxD.DLL (내용과 결합 됨) 및 MFCSxxD.LIB (정적)  
  
-   릴리스: MFCxx.DLL (내용과 결합 됨) 및 MFCSxx.LIB (정적)  
  
-   유니코드 디버그: MFCxxUD.DLL (내용과 결합 됨) 및 MFCSxxD.LIB (정적)  
  
-   유니코드 릴리스: MFCxxU.DLL (내용과 결합 됨) 및 MFCSxxU.LIB (정적)  
  
> [!NOTE]
>  MFCSxx [D] [U]입니다. LIB 라이브러리에 사용 되는 MFC와 함께 공유 Dll입니다. 이러한 라이브러리는 응용 프로그램 또는 DLL에 정적으로 연결 되어 있어야 하는 코드를 포함 합니다.  
  
 해당 가져오기 라이브러리는 응용 프로그램 연결 되어 있습니다.  
  
-   디버그: MFCxxD.LIB  
  
-   릴리스: MFCxx.LIB  
  
-   유니코드 디버그: MFCxxUD.LIB  
  
-   유니코드 릴리스: MFCxxU.LIB  
  
 "MFC 확장 DLL"은 MFCxx.DLL 기반으로 하는 DLL (및/또는 다른 MFC 공유 Dll)입니다. 여기 MFC 구성 요소 아키텍처를 시작합니다. 다른 MFC와 유사한 도구 키트를 빌드하거나는 MFC 클래스에서 유용한 클래스를 파생 하는 경우 DLL에 배치할 수 있습니다. DLL MFCxx.DLL를 사용 하 여로 최종 클라이언트 응용 프로그램을 수행 하지 않습니다. 이렇게 하면 다시 사용할 수 있는 리프 클래스, 다시 사용할 수 있는 기본 클래스 및 재사용 가능한 문서/보기 클래스 있습니다.  
  
## <a name="pros-and-cons"></a>장점 및 단점  
 MFC의 공유 버전 사용 하는 이유는  
  
-   공유 라이브러리를 사용 하 여 더 작은 응용 프로그램 (대부분의 MFC 라이브러리를 사용 하는 간단한 응용 프로그램 보다 작거나 10k) 될 수 있습니다.  
  
-   공유 버전의 MFC 기본 MFC Dll과 MFC 확장 Dll을 지원합니다.  
  
-   공유 MFC 라이브러리를 사용 하는 응용 프로그램을 작성 하는 것은 MFC를 직접 연결할 필요가 없기 때문에 정적으로 연결 된 MFC 응용 프로그램을 빌드하는 것 보다 더 빠른입니다. 특히 **디버그** 링커 디버그 정보를 압축 합니다 빌드-디버그 정보가 이미 들어 있는 DLL을 연결 하 여 응용 프로그램 내에서 압축에 디버그 정보가 적게 포함 되어 있습니다.  
  
 이유 해야 사용 하면 MFC의 공유 버전.  
  
-   MFCxx.DLL (및 기타) 배송 필요 전달 공유 라이브러리를 사용 하는 응용 프로그램과 함께 라이브러리입니다. 여러 Dll 같은 무료로 재배포할 MFCxx.DLL 이지만 여전히 항상 설치 프로그램에서 DLL를 설치 해야 합니다. 또한 프로그램와 MFC Dll 자체 둘 다에서 사용 되는 C 런타임 라이브러리를 포함 하는 MSVCRTxx.DLL를 배송 해야 합니다.  
  
##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>MFC 확장 DLL을 작성 하는 방법  
 MFC 확장명 DLL은 클래스와 MFC 클래스의 기능을 멋지게 꾸밀에 기록 하는 함수를 포함 하는 DLL입니다. MFC 확장 DLL 공유 MFC Dll을 사용 하 여 같은 방식으로 응용 프로그램,를 사용 하 여 몇 가지 사항을 추가로 고려해 야 합니다.  
  
-   빌드 프로세스 공유 MFC 라이브러리를 사용 하 여 몇 가지 추가 컴파일러 및 링커 옵션을 사용 하는 응용 프로그램을 구축 하는 것과 비슷합니다.  
  
-   MFC 확장 DLL에 없는 한 `CWinApp`-클래스를 파생 합니다.  
  
-   MFC 확장 DLL에서 특별 한을 제공 해야 `DllMain`합니다. 응용 프로그램 마법사를 제공는 `DllMain` 함수는 수정할 수 있습니다.  
  
-   MFC 확장명 DLL은 만들려는 초기화 루틴을 제공할 일반적으로 **CDynLinkLibrary** MFC 확장 DLL 하려는 경우 내보내기 `CRuntimeClass`es 또는 응용 프로그램에는 리소스입니다. 파생된 클래스의 **CDynLinkLibrary** MFC 확장 DLL에서 응용 프로그램별 데이터를 유지 해야 하는 경우 사용할 수 있습니다.  
  
 이러한 고려 사항은 아래에 자세히 설명 합니다. 또한 MFC 고급 개념 샘플을 참조 해야 [DLLHUSK](../visual-cpp-samples.md) 때문에 대해 설명 합니다.  
  
-   공유 라이브러리를 사용 하 여 응용 프로그램을 구축 합니다. (DLLHUSK 합니다. EXE는 물론 다른 Dll를 MFC 라이브러리에 동적으로 연결 하는 MFC 응용 프로그램.)  
  
-   MFC 확장 DLL을 작성 합니다. (노트 특수 플래그와 같은 `_AFXEXT` MFC 확장 DLL 작성에 사용 되는)  
  
-   MFC 확장 Dll의 두 가지 예입니다. 하나는 제한 된 내보내기 (TESTDLL1)로 MFC 확장 DLL 및 다른 표시 된 전체 클래스 인터페이스 (TESTDLL2) 내보내기의 기본 구조를 보여줍니다.  
  
 클라이언트 응용 프로그램과 모든 MFC 확장 Dll MFCxx.DLL의 동일한 버전을 사용 해야 합니다. MFC DLL 규칙을 따르는 하 고 모두 디버그를 제공 해야 하 고 소매 (/release) MFC 확장 DLL의 버전입니다. 따라서 클라이언트 프로그램을 응용 프로그램의 디버그와 일반 정품 버전을 빌드하고 적절 한 디버그 또는 모든 Dll의 정품 버전에 연결할 수 있습니다.  
  
> [!NOTE]
>  C + + 이름 변환 문제를 내보내기 때문 MFC 확장 DLL에서에서 내보내기 목록 여러 플랫폼에 대해 동일한 DLL의 디버그 버전과 소매 마다 다를 수 있습니다. 소매 MFCxx.DLL에 약 2000 내보낸 진입점이 있습니다. 디버그 MFCxxD.DLL에 약 3000 내보낸 진입점입니다.  
  
### <a name="quick-note-on-memory-management"></a>메모리 관리에 대 한 빠른 참고  
 "메모리 관리,"이 기술 노트의 끝 부분에서 섹션 MFCxx.DLL 공유 버전의 MFC 구현에 설명 합니다. DLL 여기에 설명 된는 MFC 확장을 구현 하기 위해 알아야 할 정보입니다.  
  
 MFCxx.DLL 및 클라이언트 응용 프로그램의 주소 공간으로 로드 된 모든 MFC 확장 Dll 동일한 메모리 할당자, 및을 사용할 리소스 로드 MFC "전역" 상태 다른 동일한 응용 프로그램에서 듯 합니다. 비 MFC DLL 라이브러리와 MFC에 정적으로 링크 하는 기본 MFC Dll에는 정반대 작업을 수행 하며 각 DLL이 프로그램은 자체 메모리 풀에서 할당 하도록 하므로이 기능은 중요 합니다.  
  
 MFC 확장 DLL이 메모리를 할당 하는 경우 다음 해당 메모리 자유롭게 혼합 될 수 있습니다 다른 응용 프로그램에서 할당 된 개체를 사용 합니다. 또한 공유 MFC 라이브러리를 사용 하는 응용 프로그램의 작동이 중단 하는 경우 보호는 운영 체제의 해당 DLL을 공유 하는 다른 MFC 응용 프로그램의 무결성이 유지 됩니다.  
  
 마찬가지로 다른 "전역" MFC 상태는 리소스를 로드 하 여 현재 실행 파일과 같은 클라이언트 응용 프로그램 및 모든 MFC 확장 Dll으로 자체 MFCxx.DLL 간에 공유 됩니다.  
  
### <a name="building-an-mfc-extension-dll"></a>MFC 확장 DLL 작성  
 응용 프로그램 마법사를 사용 하 여 MFC 확장 DLL 프로젝트를 만들려면 하 고 적절 한 컴파일러와 링커 설정이 자동으로 생성 됩니다. 또한 생성 된는 `DllMain` 함수는 수정할 수 있습니다.  
  
 MFC 확장 DLL 기존 프로젝트를 변환 하는 경우 공유 버전의 MFC 사용 하 여 응용 프로그램을 구축 하기 위한 표준 규칙으로 시작 하 고 다음을 수행 합니다.  
  
-   추가 **/D_AFXEXT** 컴파일러 플래그를 합니다. 프로젝트 속성 대화 상자에서 C/c + + 노드를 선택 합니다. 다음 전처리기 범주를 선택 합니다. 추가 `_AFXEXT` 매크로 정의 필드에 각 항목의 세미콜론으로 구분 합니다.  
  
-   제거는 **/Gy** 컴파일러 스위치입니다. 프로젝트 속성 대화 상자에서 C/c + + 노드를 선택 합니다. 다음 코드 생성 범주를 선택 합니다. "함수 수준 링크 사용" 옵션 설정 되어 있지 않은지 확인 합니다. 이 쉽게 클래스를 내보내면 있으므로 링커가 참조 되지 않는 함수를 제거 하지 것입니다. MFC DLL 변경 MFC에 정적으로 링크는 원래 프로젝트 일반 빌드에 사용 되는 경우는 **/MT [d]** 컴파일러 옵션을 **/MD [d]**합니다.  
  
-   와 내보내기 라이브러리인 빌드는 **/DLL** 링크 하는 옵션입니다. 이 대상 유형으로 Win32 동적 연결 라이브러리를 지정 하는 새 대상을 만들 때 설정 됩니다.  
  
### <a name="changing-your-header-files"></a>헤더 파일 변경  
 MFC 확장 DLL의 목표는 일반적으로 해당 기능을 사용할 수 있는 하나 이상의 응용 프로그램에 몇 가지 일반적인 기능을 내보내려면 합니다. 이 클래스와 클라이언트 응용 프로그램에 사용할 수 있는 전역 함수 내보내기에 따라 결정 합니다.  
  
 이 작업을 수행 하기 위해 가져오거나 적절 하 게 내보낼 처럼 표시 되어 멤버 함수는 각각 되도록 해야 합니다. 이 위해서는 특수 선언: **__declspec (dllexport)** 및 **__declspec (dllimport)**합니다. 클래스는 클라이언트 응용 프로그램에서 사용 되는 경우 원하는로 선언 해야 **__declspec (dllimport)**합니다. MFC 확장 DLL 자체를 작성할 때 것으로 선언 해야 **__declspec (dllexport)**합니다. 또한 함수가 실제로 내보내야 하며, 클라이언트 프로그램을 로드할 때 바인딩하고 되도록 합니다.  
  
 전체 클래스를 내보내려면 **AFX_EXT_CLASS** 클래스 정의에 있습니다. 이 매크로로 프레임 워크에 의해 정의 된 **__declspec (dllexport)** 때 **_AFXDLL** 및 `_AFXEXT` 정의 되지만로 정의 **__declspec (dllimport)** 때 `_AFXEXT` 정의 되어 있지 않습니다. `_AFXEXT`MFC 확장 DLL을 빌드하는 경우에 위에서 설명한 대로 정의 됩니다. 예:  
  
```  
class AFX_EXT_CLASS CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않는 경우  
 따라 클래스의 필요한 개별 구성원만 내보낼 할 수도 있습니다. 예를 들어, 내보내는 경우는 `CDialog`-파생 클래스 생성자는 내보낼 하기만 하면 및 `DoModal` 호출 합니다. DLL의를 사용 하 여 이러한 멤버를 내보낼 수 있습니다. DEF 파일 있지만 있습니다 사용할 수도 **AFX_EXT_CLASS** 내보내야 하는 개별 멤버에 거의 동일한 방법으로 합니다.  
  
 예:  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
    AFX_EXT_CLASS CExampleDialog();
AFX_EXT_CLASS int DoModal();
*// rest of class definition  
 .  
 .  
 .  
};  
```  
  
 이 작업을 수행 하는 경우 클래스의 모든 멤버를 더 이상 내보내지 않으므로 때문에 한 추가 문제가 발생할 수 없습니다. MFC 매크로 작동 방식에서에 문제가 있습니다. 일부 MFC의 도우미 매크로 실제로 선언 하거나 데이터 멤버를 정의 합니다. 따라서 이러한 데이터 멤버를 DLL에서 내보낼 수 해야 합니다.  
  
 예를 들어는 `DECLARE_DYNAMIC` 매크로 MFC 확장 DLL을 빌드할 때 다음과 같이 정의 됩니다.  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
    static CRuntimeClass* PASCAL _GetBaseClass();

\  
    public: \  
    static AFX_DATA CRuntimeClass class##class_name; \  
    virtual CRuntimeClass* GetRuntimeClass() const;

\  
```  
  
 시작 하는 줄 "정적 `AFX_DATA`" 클래스 내부에서 정적 개체를 선언 합니다. 이 클래스를 올바르게 내보내고 클라이언트에서 런타임 정보에 액세스 합니다. EXE를이 정적 개체를 내보낼 필요가 있습니다. 정적 개체는 한정자로 선언 되었으므로 `AFX_DATA`를 정의 해야 `AFX_DATA` 되도록 **__declspec (dllexport)** DLL을 빌드할 때 정의 **__declspec (dllimport)** 클라이언트를 실행 파일을 빌드하는 경우.  
  
 위에서 설명 했 듯이 **AFX_EXT_CLASS** 이런 방식이으로에 이미 정의 되었습니다. 다시 정의 해야 `AFX_DATA` 와 동일 하 게 **AFX_EXT_CLASS** 주위 클래스 정의 합니다.  
  
 예:  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
class CExampleView : public CView  
{  
    DECLARE_DYNAMIC() *// ... class definition ...  
};  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 MFC 사용 하 여 항상는 `AFX_DATA` 이러한 모든 시나리오에이 기술을 작동 하도록 해당 매크로 내에서 정의 하는 데이터 항목에는 기호입니다. 에 사용할 수는 예를 들어 `DECLARE_MESSAGE_MAP`합니다.  
  
> [!NOTE]
>  클래스의 선택한 멤버 보다는 전체 클래스를 내보내는 경우 정적 데이터 멤버가 자동으로 내보내집니다.  
  
 동일한 기법을 사용 하 여 자동으로 내보내기는 `CArchive` 추출 연산자를 사용 하는 클래스는 `DECLARE_SERIAL` 및 `IMPLEMENT_SERIAL` 매크로입니다. 대괄호 클래스 선언 하 여 보관 연산자를 내보냅니다 (에 합니다. H 파일)를 다음 코드로:  
  
```  
#undef AFX_API  
#define AFX_API AFX_EXT_CLASS  
 
<your class declarations here>  
 
#undef AFX_API  
#define AFX_API  
```  
  
### <a name="limitations-of-afxext"></a>_AFXEXT의 제한 사항  
 _를 사용할 수 있습니다**AFXEXT** MFC 확장 Dll 오지 않아도 MFC 확장 Dll의 여러 계층에 전처리기 기호입니다. MFC 확장 호출 또는 사용자의 MFC 확장 Dll MFC 클래스에서 다음 파생 되는 클래스에서 파생 되는 Dll이 있는 경우에 모호성을 피하기 위해 사용자 고유의 전처리기 기호를 사용 해야 합니다.  
  
 이 문제는 해당에 Win32, 모든 데이터를 명시적으로 선언 해야 **__declspec (dllexport)** DLL에서 가져와야 하는 경우 및 **__declspec (dllimport)** DLL에서 가져와야 하는 경우. 정의 하는 경우 `_AFXEXT`, MFC 헤더 되도록 **AFX_EXT_CLASS** 제대로 정의 됩니다.  
  
 있는 경우 여러 개의 레이어, 하나의 기호와 같은 **AFX_EXT_CLASS** MFC 확장 DLL 있습니다 수 새 클래스를 내보낼 뿐만 아니라 다른 MFC 확장 DLL에서에서 다른 클래스를 가져올 이후 충분 하지 않습니다. 이 문제를 해결 하기 위해 작성할 수 있도록 DLL 자체 DLL을 사용 하 여 비교를 나타내는 특수 전처리기 기호를 사용 합니다. 예를 들어 두 개의 MFC 확장 Dll, A.DLL, 및 B.DLL 한다고 가정 합니다. 구성 파일은 각각의 일부 클래스 A.H와 B.H에 각각 내보냅니다. B.DLL은 A.DLL에서 클래스를 사용 합니다. 헤더 파일 모양은 다음과 같습니다.  
  
```  
/* A.H */  
#ifdef A_IMPL  
 #define CLASS_DECL_A   __declspec(dllexport)  
#else  
 #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
 
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
 
/* B.H */  
#ifdef B_IMPL  
 #define CLASS_DECL_B   __declspec(dllexport)  
#else  
 #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
 
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition .. };  
```  
  
 사용 하 여 빌드 A.DLL를 빌드할 때 **/D A_IMPL** 사용 하 여 빌드 B.DLL를 빌드할 때 및 **/D B_IMPL**합니다. 각 DLL에 대 한 별도 기호를 사용해 CExampleB 내보내집니다이 고 B.DLL를 빌드할 때 CExampleA 가져옵니다. CExampleA는 A.DLL 빌드될 때 이며 B.DLL (또는 다른 클라이언트)가 사용 될 때 가져오게 됩니다.  
  
 기본 제공을 사용 하는 경우 이러한 유형의 쌓기를 수행할 수 없는 **AFX_EXT_CLASS** 및 `_AFXEXT` 전처리기 기호입니다. 위에서 설명한 기술을 자체 MFC 메커니즘에는 해당 OLE, 데이터베이스 및 네트워크 MFC 확장 Dll을 빌드할 때 사용 하 방식으로이 문제를 해결 합니다.  
  
### <a name="not-exporting-the-entire-class"></a>전체 클래스를 내보내지 않는 경우  
 다시, 전체 클래스를 내보내지 않는 경우 각별히 주의 해야 합니다. MFC 매크로로 만들어 필요한 데이터 항목 내보내집니다 확인 해야 합니다. 다시 정의 하 여이 작업을 수행할 수 있습니다 **AFX_DATA** 특정 클래스의 매크로를 합니다. 이렇게 해야 전체 클래스를 내보내지 않는 언제 든 지 합니다.  
  
 예:  
  
```  
// A.H  
#ifdef A_IMPL  
 #define CLASS_DECL_A  _declspec(dllexport)  
#else  
 #define CLASS_DECL_A  _declspec(dllimport)  
 #endif  
 
#undef  AFX_DATA  
#define AFX_DATA CLASS_DECL_A  
 
class CExampleA : public CObject  
{  
    DECLARE_DYNAMIC() 
    CLASS_DECL_A int SomeFunction();
*//class definition   
 .  
 .  
 .  
};  
 
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### <a name="dllmain"></a>DllMain  
 다음은 MFC 확장 DLL에 대 한 주 소스 파일에 배치 해야 하는 정확한 코드입니다. 표준에 포함 된 다음 이어야 합니다. 응용 프로그램 마법사를 사용 하 여 MFC 확장 DLL에 대 한 시작 파일을 만들 때 제공 참고는 `DllMain` 드립니다.  
  
```  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE extensionDLL;  
  
extern "C" int APIENTRY   
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      // MFC extension DLL one-time initialization   
      if (!AfxInitExtensionModule(  
             extensionDLL, hInstance))  
         return 0;  
  
      // TODO: perform other initialization tasks here  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      // MFC extension DLL per-process termination  
      AfxTermExtensionModule(extensionDLL);  
  
          // TODO: perform other cleanup tasks here  
   }  
   return 1;   // ok  
}  
```  
  
 에 대 한 호출 `AfxInitExtensionModule` 모듈 런타임 클래스를 캡처합니다 (`CRuntimeClass` 구조)의 개체 팩터리 뿐만 아니라 (`COleObjectFactory` 개체) 사용 하기 위해 뒷부분에 나오는 경우에는 **CDynLinkLibrary** 개체가 만들어집니다. (선택 사항) 호출 `AfxTermExtensionModule` 허용 MFC 정리에 MFC 확장 DLL 각 프로세스를 분리할 경우 (때나의 결과로 DLL이 언로드되어 프로세스가 종료 될 때 발생 하는 **FreeLibrary** 호출) MFC 확장 DLL에서 . 이후 대부분 MFC 확장 Dll을 동적으로 로드 되지 않습니다 (일반적으로 연결 된 해당 가져오기 라이브러리를 통해)에 대 한 호출 `AfxTermExtensionModule` 일반적으로 필요 하지 않습니다.  
  
 응용 프로그램을 로드 하 MFC 확장 Dll을 동적으로 확보 하는 경우 호출 해야 `AfxTermExtensionModule` 위와 같이 합니다. 또한 사용 해야 `AfxLoadLibrary` 및 `AfxFreeLibrary` (Win32 함수 대신 **LoadLibrary** 및 **FreeLibrary**) 또는 MFC를 동적으로 로드 되는 경우 응용 프로그램은 여러 스레드를 사용 하는 경우 확장 DLL입니다. 사용 하 여 `AfxLoadLibrary` 및 `AfxFreeLibrary` MFC 확장 DLL이 로드 되거나 언로드될 때 실행 되는 시작 및 종료 코드 전역 MFC 상태가 손상 되지 않는 시나리오입니다.  
  
 헤더 파일 AFXDLLX입니다. 에 대 한 정의와 같은 MFC 확장 Dll에서 사용 되는 구조에 대 한 특별 한 정의 포함 하는 H `AFX_EXTENSION_MODULE` 및 **CDynLinkLibrary**합니다.  
  
 전역 *extensionDLL* 표시 된 것으로 선언 해야 합니다. 16 비트 버전의 MFC와는 달리 메모리를 할당할를 시간순으로 MFCxx.DLL 완전히 초기화 된 후이 시간 동안 MFC 함수를 호출할 수 있습니다 프로그램 `DllMain` 호출 됩니다.  
  
### <a name="sharing-resources-and-classes"></a>공유 리소스 및 클래스  
 간단한 MFC 확장 Dll 클라이언트 응용 프로그램에 아무 것도 더 몇 가지 낮은 대역폭 함수를 내보낼만 필요 합니다. 더 많은 사용자 인터페이스 집약적인 Dll 리소스와 c + + 클래스를 클라이언트 응용 프로그램 내보낼 수도 있습니다.  
  
 리소스 내보내기 리소스 목록을 통해 수행 됩니다. 각 응용 프로그램에는 단일 연결된 목록이 **CDynLinkLibrary** 개체입니다. 대부분의 리소스를 로드 하는 표준 MFC 구현에서는 현재 리소스 모듈에서 먼저 찾습니다 리소스를 찾을 때는 (`AfxGetResourceHandle`) 및 워크 찾을 수 없습니다. 목록 **CDynLinkLibrary** 로드 하려고 하는 개체는 요청 된 리소스입니다.  
  
 C + + 클래스 이름이 지정 된 c + + 개체의 동적 생성은 유사 합니다. MFC 개체의 deserialization 메커니즘의 일부 요구 된 `CRuntimeClass` 개체를 등록 하 여 동적으로 저장 된 순서에 따라 필요한 형식의 c + + 개체를 만들거나 다시 구성할 수 있습니다.  
  
 MFC 확장 DLL에에서 클래스를 사용 하도록 클라이언트 응용 프로그램 `DECLARE_SERIAL`, 클라이언트 응용 프로그램에 표시 되도록 클래스를 내보낼 해야 합니다. 검색 하 여도 이렇게는 **CDynLinkLibrary** 목록입니다.  
  
 MFC 고급 개념 샘플의 경우 [DLLHUSK](../visual-cpp-samples.md), 같이 목록을 표시 합니다.  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
 |      |  
    TESTDLL2.DLL TESTDLL2.DLL  
 |      |  
    TESTDLL1.DLL TESTDLL1.DLL  
 |      |  
 |      |  
    MFC90D.DLL MFC90.DLL  
```  
  
 MFCxx.DLL은 대개 마지막 리소스 및 클래스 목록에 있습니다. MFCxx.DLL 모든 모든 표준 명령 Id에 대 한 프롬프트 문자열을 포함 하 여 표준 MFC 리소스를 포함 합니다. Dll과 클라이언트 응용 프로그램 자체에 없는 목록의 끝에 배치 될 수 있습니다는 표준 MFC 리소스에는 공유의 리소스에 의존 MFCxx.DLL 대신 하지만 자체 복사본입니다.  
  
 클라이언트 응용 프로그램의 네임 스페이스에는 리소스 및 모든 Dll의 클래스 이름을 병합 하는 것에 어떤 Id 않도록 주의 해야 하는 단점이 또는 이름을 선택할 수 있습니다. 물론 여 비활성화할 수 있습니다이 기능 중 하나를 내보내지 않는 경우 리소스 또는 **CDynLinkLibrary** 클라이언트 응용 프로그램에는 개체입니다. [DLLHUSK](../visual-cpp-samples.md) 샘플에서는 여러 헤더 파일을 사용 하 여 공유 리소스 네임 스페이스를 관리 합니다. 참조 [기술 참고 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 자세한 방법에 대 한 공유 리소스 파일을 사용 합니다.  
  
### <a name="initializing-the-dll"></a>DLL 초기화  
 위에서 설명 했 듯이 일반적으로 만들려는 **CDynLinkLibrary** 클라이언트 응용 프로그램 리소스 및 클래스를 내보내려면 개체입니다. DLL 초기화에 대 한 내보낸된 진입점을 제공 해야 합니다. 최소한,이 인수가 없는 하 고 아무 것도 반환 하는 void 루틴 이지만 필요 하면 수 있습니다.  
  
 이 방법을 사용 하면 DLL을 사용 하는 각 클라이언트 응용 프로그램이 초기화 루틴을 호출 해야 합니다. 이 할당할 수도 있습니다 **CDynLinkLibrary** 개체 프로그램 `DllMain` 호출 후 바로 `AfxInitExtensionModule`합니다.  
  
 초기화 루틴을 만들어야는 **CDynLinkLibrary** MFC 확장 DLL 정보 된 현재 응용 프로그램의 힙에서 개체입니다. 다음 항목과 작업을 수행할 수 있습니다.  
  
```  
extern "C" extern void WINAPI InitXxxDLL()  
{  
    new CDynLinkLibrary(extensionDLL);

}  
```  
  
 루틴 이름을 *InitXxxDLL* 이 예제에서는 원하는 대로 될 수 있습니다. 될 필요가 없습니다 `extern "C"`, 그렇게 쉽게 유지 관리 하는 내보내기 목록 하지만 합니다.  
  
> [!NOTE]
>  일반 MFC DLL에서에서 MFC 확장 DLL을 사용 하는 경우이 초기화 함수를 내보내야 합니다. 이 함수는 MFC 확장 DLL 클래스 또는 리소스를 사용 하기 전에 일반적인 MFC DLL에서 호출 되어야 합니다.  
  
### <a name="exporting-entries"></a>항목 내보내기  
 프로그램 클래스를 내보내면 간단한 방법을 사용 하는 것 **__declspec (dllimport)** 및 **__declspec (dllexport)** 각 클래스 및 전역 함수를 내보내려면 합니다. 이 사용 하면 훨씬 쉽게 하지만 어떤 함수는 내보내집니다 제어할 있고 서 수로 함수를 내보낼 수 없습니다 (아래 설명 참조) 각 진입점 이름이 보다 효율성이 떨어집니다. TESTDLL1 및 TESTDLL2 내보낼 항목의이 메서드를 사용 합니다.  
  
 각 항목의 이름을 지정 하 여 각 항목을 수동으로 내보낼 하는 것 보다 효율적인 메서드 (및 MFCxx.DLL 사용 하는 방법)는입니다. DEF 파일입니다. (즉, 것은 아닙니다) DLL에서 선택적 내보내기의 내보내는 것 때문 내보낼을 특정 인터페이스를 결정 해야 합니다. 에 있는 항목의 형태로 링커에 형식 표시 이름을 지정 해야 하므로 어렵습니다는 합니다. DEF 파일입니다. 것에 대 한 기호화 된 링크를 포함 하는 데 필요한 것 하지 않는 한 모든 c + + 클래스를 내보내지 마십시오.  
  
 시도한 경우 내보내기 c + + 클래스와 한입니다. DEF 파일을 이전에이 목록을 자동으로 생성 하는 도구를 개발 하는 것이 좋습니다. 이렇게 하는 링크 2 단계 프로세스를 사용 하 여 합니다. 없는 내보내기로 한 번 DLL에 연결 하 고 생성 하도록 링커에 수는 있습니다. 맵 파일입니다. 합니다. 되므로 일부 다시 정렬 사용에 대 한 내보내기 항목 생성에 사용할 수 있습니다를 내보내야 하는 함수의 목록을 생성 하려면 맵 파일을 사용할 수 있습니다 프로그램. DEF 파일입니다. OLE MFCxx.DLL 및 번호, 천 여러 데이터베이스 MFC 확장 Dll에 대 한 내보내기 목록 (완전히 자동이 하 고 잠시 후에 이따금 튜닝 일부 손 필요) 있지만 이러한 프로세스와 생성 되었습니다.  
  
### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs입니다. CDynLinkLibrary  
 MFC 확장 DLL에 없는 한 `CWinApp`-파생 개체 자체의; 대신 사용 해야는 `CWinApp`-클라이언트 응용 프로그램의 개체를 파생 합니다. 이 클라이언트 응용 프로그램 등 유휴 루프가 기본 메시지 펌프를 소유 함을 의미 합니다.  
  
 새 클래스를 파생 시켜 MFC 확장 DLL을 각 응용 프로그램에 대 한 추가 데이터를 유지 관리 하는 경우 **CDynLinkLibrary** 위에 설명 된 루틴 InitXxxDLL에 만듭니다. DLL의 현재 응용 프로그램의 목록을 확인할 수를 실행할 때 **CDynLinkLibrary** 해당 특정 MFC 확장 DLL에 대 한 찾을 개체입니다.  
  
### <a name="using-resources-in-your-dll-implementation"></a>리소스 DLL 구현에서 사용 하 여  
 기본 리소스 부하의 목록으로 이동 됩니다 위에서 설명 했 듯이 **CDynLinkLibrary** 첫 번째 EXE 또는 DLL가 요청된 된 리소스를 찾고 개체입니다. MFC는 모든 Api 뿐만 아니라 내부 코드를 사용 하 여 모든 `AfxFindResourceHandle` 에 상주할 수 있습니다에 관계 없이 모든 리소스를 찾을 리소스 목록으로 이동 합니다.  
  
 Api를 사용 하 여만 특정 위치에서 리소스를 로드 하려는 경우 `AfxGetResourceHandle` 및 `AfxSetResourceHandle` 하 기존 핸들을 저장 하 고 새 핸들을 설정 합니다. 클라이언트 응용 프로그램에 반환 하기 전에 이전 리소스 핸들을 복원 해야 합니다. 샘플 TESTDLL2 메뉴를 명시적으로 로드 하기 위한이 접근 방식을 사용 합니다.  
  
 목록 트래버스 단점이 약간 느려질 것 및 리소스 ID 범위 관리를 필요로 합니다. MFC 확장 Dll이 몇 개에 연결 하는 클라이언트 응용 프로그램 DLL 인스턴스 핸들을 지정 하지 않고도 DLL에서 제공 하는 리소스를 사용할 수 있다는 이점이 있습니다. `AfxFindResourceHandle`API는 순환 리소스 목록에 대 한 지정 된 일치 하는 합니다. 이름 및 리소스의 형식을 사용 해야 하 고 처음 발견 되는 리소스 핸들 (또는 NULL)를 반환 합니다.  
  
##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL 버전을 사용 하 여 응용 프로그램 작성  
  
### <a name="application-requirements"></a>응용 프로그램 요구 사항  
 MFC의 공유 버전을 사용 하는 응용 프로그램 몇 가지 간단한 규칙을 따라야 합니다.  
  
-   있어야는 `CWinApp` 개체를 메시지 펌프에 대 한 표준 규칙을 따릅니다.  
  
-   필요한 컴파일러 플래그 (아래 참조)의 집합과 컴파일해야 합니다.  
  
-   MFCxx 가져오기 라이브러리와 연결 해야 합니다. 필요한 컴파일러 플래그를 설정 하 여 MFC 헤더 확인 링크 타임에 상위 라이브러리를 사용 하 여 응용 프로그램 링크 해야 합니다.  
  
-   실행 파일을 실행 하려면 MFCxx.DLL Windows 시스템 디렉터리에서 또는 경로에 있어야 합니다.  
  
### <a name="building-with-the-development-environment"></a>개발 환경을 구축  
 내부 메이크파일 대부분의 표준 기본값을 사용 하는 경우 DLL 버전을 빌드하려면 프로젝트를 쉽게 변경할 수 있습니다.  
  
 다음 단계에서는 NAFXCWD로 연결 된 올바르게 작동 MFC 응용 프로그램을 가정 합니다. (디버그)에 대 한 LIB 고 NAFXCW 합니다. LIB (정품)에 대 한 하려면 공유에서 버전의 MFC 라이브러리를 사용 하도록 변환 합니다. Visual c + + 환경을 실행 중인 및 내부 프로젝트 파일이 있어야 합니다.  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 에 **일반** 페이지 **프로젝트 기본값**, Microsoft Foundation Classes 설정 **공유 DLL에서 MFC 사용** (MFCxx(d).dll) 합니다.  
  
### <a name="building-with-nmake"></a>NMAKE로 작성  
 Visual c + +의 외부 메이크파일을 기능을 사용 하는 하거나 NMAKE를 직접 사용 하는 경우 컴파일러 및 링커 옵션을 지원 하기 위해 메이크파일을 편집 해야 합니다.  
  
 필요한 컴파일러 플래그:  
  
 **/ D_AFXDLL /MD**  
 **/ D_AFXDLL**  
  
 표준 MFC 헤더에는이 기호를 정의할 수 필요 합니다.  
  
 **/MD**  
 C 런타임 라이브러리의 DLL 버전을 사용 해야 하는 응용 프로그램  
  
 다른 모든 컴파일러 플래그 (예를 들어 디버깅용 _DEBUG) MFC 기본값을 따릅니다.  
  
 라이브러리 링커 목록을 편집 합니다. NAFXCWD 변경 합니다. LIB MFCxxD.LIB을을 선택 하 고 NAFXCW 변경 합니다. LIB MFCxx.LIB 하 합니다. LIBC를 대체 합니다. MSVCRT와 LIB 합니다. LIB 합니다. 다른 MFC 라이브러리와 MFCxxD.LIB 배치는 중요 한 이므로 **하기 전에** 모든 C 런타임 라이브러리입니다.  
  
 필요에 따라 추가 **/D_AFXDLL** 소매 및 디버그 둘 다 리소스 컴파일러 옵션 (실제로 사용 하 여 리소스를 컴파일하고 한 **/R**). 그러면 최종 실행 파일 더 작은 MFC Dll에 있는 리소스를 공유 합니다.  
  
 이러한 변경 된 후 전체를 다시 빌드해야가 필요 합니다.  
  
### <a name="building-the-samples"></a>샘플 빌드  
 명령줄에서 공유 호환 NMAKE 메이크파일 또는 Visual c + +에서 대부분의 MFC 샘플 프로그램을 빌드할 수 있습니다.  
  
 MFCxx.DLL 사용할 이러한 샘플 중 하나를 변환 하려면 로드할 수는 있습니다. MAK Visual c + +로 파일을 위에서 설명한 것 처럼 프로젝트 옵션을 설정 합니다. 경우에 NMAKE 빌드를 사용 하는, 지정할 수 있습니다 "AFXDLL = 1" NMAKE 명령줄을 사용 하는 구축할 기반 공유 MFC 라이브러리를 사용 하는 샘플입니다.  
  
 MFC 고급 개념 샘플 [DLLHUSK](../visual-cpp-samples.md) MFC의 DLL 버전에 두고 작성 되었습니다. 이 샘플에는 뿐만 아니라 MFCxx.DLL로 연결 된 응용 프로그램을 빌드하는 방법을 설명 하지만 MFC DLL 패키징 옵션 MFC 확장 Dll이 기술 노트의 뒷부분에 나오는 설명 등의 다른 기능 보여 줍니다.  
  
### <a name="packaging-notes"></a>패키지 정보  
 소매 버전의 Dll (MFCxx [U]. DLL)은 자유롭게 재배포할 수 있습니다. Dll의 디버그 버전은 자유롭게 재배포할 수 없으며 응용 프로그램의 개발 중에 사용 해야 합니다.  
  
 디버그 Dll 디버깅 정보로 제공 됩니다. Visual c + + 디버거를 사용 하 여 DLL 뿐만 아니라 응용 프로그램의 실행을 추적할 수 있습니다. 릴리스 Dll (MFCxx [U]. DLL) 디버깅 정보가 포함 되지 않습니다.  
  
 를 사용자 지정 하거나 Dll을 다시 작성 하는 경우 다음 있습니다 호출 해야 문제가 "MFCxx" The MFC SRC 파일 MFCDLL 이외의 합니다. 빌드 옵션을 설명 하 고 DLL 이름을 변경 하기 위한 논리를 포함 하는 MAK입니다. 이러한 Dll 공유 되는 경우가 많은 MFC 응용 프로그램에 있으므로 파일 이름 바꾸기 작업은 필요 합니다. 사용자 지정 버전의 MFC Dll 바꾸기 있는 시스템에 설치 된 공유 MFC Dll을 사용 하 여 다른 MFC 응용 프로그램을 바꿀 수 있습니다.  
  
 MFC Dll을 다시 작성 하면 권장 되지 않습니다.  
  
##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL 구현 방법  
 다음 섹션에서는 MFC DLL (MFCxx.DLL 및 MFCxxD.DLL)를 구현 하는 방법을 설명 합니다. 여기에 세부 정보 없는 이해 모든 수행 하려는 경우를 중요 응용 프로그램과 함께 MFC DLL을 사용 합니다. 여기에 세부 정보는 MFC 확장 DLL을 작성 하는 방법을 이해 하는 데 필수적이 지 않은 하지만이 구현을 이해 사용자 고유의 DLL을 작성 하는 데 도움이 될 수 있습니다.  
  
### <a name="implementation-overview"></a>구현 개요  
 MFC DLL은 위에서 설명한 것 처럼 MFC 확장 DLL의 특수 한 경우 실제로 합니다. 다양 한 클래스에 대 한 내보내기 매우 큰이 번호가 있습니다. 일반 MFC 확장 DLL 보다 훨씬 더 특수 하는 몇 가지 추가 사항을 MFC DLL에서 작업을 수행 하기 있습니다.  
  
### <a name="win32-does-most-of-the-work"></a>Win32는 대부분의 작업  
 16 비트 버전의 MFC 다양 한 앱 별 데이터를 포함 한 스택 세그먼트 일부 80x86 어셈블리 코드, 프로세스별 예외 컨텍스트 및 기타 기술에서 만든 특수 한 세그먼트 특수 기술이 필요 합니다. Win32 직접 데이터를 지원 프로세스별 DLL에서가 원하는 대부분의 시간입니다. 대부분의 경우 MFCxx.DLL NAFXCW 뿐입니다. LIB DLL 파일로 패키지 합니다. MFC 소스 코드를 보면 수행 되어야 하는 특수 한 상황이 거의 있으므로 매우 적은 #ifdef _AFXDLL을 찾을 수 있습니다. 없는 특별히 Windows 3.1 (Win32s 라고도 함)에 Win32을 처리 하는 특수 한 경우 Win32s는 MFC DLL 스레드 로컬 저장소 (TLS) 프로세스 로컬 데이터를 가져오기 위해 Win32 Api 사용 해야 하므로 직접 프로세스별 DLL 데이터를 지원 하지 않습니다.  
  
### <a name="impact-on-library-sources-additional-files"></a>원본 라이브러리 추가 파일에 대 한 영향  
 영향은 **_AFXDLL** 일반적인 MFC 클래스 라이브러리 소스 및 헤더에서 버전은 비교적 적습니다. 특수 버전 파일이 (AFXV_DLL 합니다. H) 뿐만 아니라 추가 헤더 파일 (AFXDLL_ 합니다. H) 주 AFXWIN으로 포함 합니다. H 헤더입니다. AFXDLL_ 합니다. H 헤더에 포함 됩니다는 **CDynLinkLibrary** 클래스 및 기타 구현 세부 사항을 모두 **_AFXDLL** 응용 프로그램 및 MFC 확장 Dll입니다. AFXDLLX 합니다. MFC 확장명 Dll (자세한 내용은 위 참조)를 구축 하기 위한 H 헤더 파일에 제공 됩니다.  
  
 MFC 라이브러리 MFC SRC에 일반 원본에서 추가 조건부 코드에는 **_AFXDLL** #ifdef 합니다. 추가 원본 파일 (DLLINIT 합니다. 추가 DLL 초기화 코드와 공유 버전의 MFC에 대 한 다른 붙이기 CPP)에 포함 되어 있습니다.  
  
 MFC의 공유 버전을 생성 하려면 추가 파일이 제공 됩니다. (아래 참조 DLL을 작성 하는 방법에 대 한 내용은.)  
  
-   두 가지입니다. DEF 파일을 디버그 (MFCxxD.DEF)에 대 한 MFC DLL 진입점을 내보내는 데 사용 되 고 릴리스 DLL의 버전 (MFCxx.DEF).  
  
-   합니다. RC 파일 (MFCDLL 합니다. RC) DLL에 대 한 모든 표준 MFC 리소스 및 VERSIONINFO 리소스를 포함합니다.  
  
-   A입니다. CLW 파일 (MFCDLL 합니다. CLW) 클래스 마법사를 사용 하 여 클래스는 MFC 검색을 허용 하도록 제공 됩니다. 참고:이 기능은 MFC의 DLL 버전에 따라 다를 않습니다.  
  
### <a name="memory-management"></a>메모리 관리  
 MFCxx.DLL를 사용 하 여 응용 프로그램 MSVCRTxx.DLL, 공유 C 런타임 DLL에서 제공 되는 일반적인 메모리 할당자를 사용 합니다. 응용 프로그램, 모든 MFC 확장명 Dll과 자체는 MFC Dll이 공유 메모리 할당자를 사용합니다. 공유 DLL 메모리 할당에 대 한를 사용 하 여 MFC Dll 응용 프로그램에 의해, 또는 그 반대로 해제 나중에 메모리를 할당할 수 있습니다. 전역 c + +를 재정의 하지 않아야 함 응용 프로그램과 DLL 동일한 할당자를 사용 해야 하므로 `operator new` 또는 `operator delete`합니다. C 런타임 메모리 할당 루틴의 나머지 부분에는 동일한 규칙이 적용 (같은 `malloc`, `realloc`, **무료**, 등).  
  
### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>서 수 및 클래스 __declspec (dllexport) 및 DLL 이름 지정  
 사용 하지 않습니다는 `class` **__declspec (dllexport)** c + + 컴파일러의 기능입니다. 대신, export 목록 (MFCxx.DEF 및 MFCxxD.DEF) 클래스 라이브러리 소스 포함 되어 있습니다. 진입점 (함수 및 데이터)의 선택이 집합에만 내보내집니다. MFC private 구현 함수 또는 클래스 등의 다른 기호는 내보내지지 않습니다 내보내기를 모두 상주 또는 비 상주 이름 테이블에는 문자열 이름이 없는 서 수로 수행 됩니다.  
  
 사용 하 여 `class` **__declspec (dllexport)** 효율성과 용량을 대 안으로 이용할 작은 Dll을 작성 하기 위한 하지만 메커니즘을 내보내는 기본 MFC와 같은 큰 DLL의 경우에 수 제한 합니다.  
  
 즉, 모든 이란 많은 양의 릴리스의 MFCxx.DLL 많이 실행을 손상 시 키 지 또는 속도 로드 하지 않고 약 800 KB만 있는 기능은 패키지할 수 있습니다. MFCxx.DLL 있었을 100k 큰이 기술은 되지 않은 사용 합니다. 이 인해 추가 진입점의 끝에 추가할 수는 있습니다. 서 수로 내보내기의 속도 크기 효율성을 유지 하면서 단순 버전 관리를 허용 하도록 DEF 파일입니다. MFC 클래스 라이브러리에 있는 주 버전 수정 라이브러리 이름을 변경 됩니다. 즉, MFC30 합니다. DLL은 MFC 클래스 라이브러리의 버전 3.0에 포함 된 재배포 가능 DLL입니다. 이 DLL 업그레이드 하는 예를 들어, 가상 MFC 3.1에서는 MFC31 DLL 이름을 지정 합니다. DLL 대신 합니다. 를 사용자 지정 버전의 MFC DLL을 생성 하는 MFC 소스 코드를 수정 하는 경우 사용 하 여 다른 이름을 (및 가급적 없는 이름에 "MFC").  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

