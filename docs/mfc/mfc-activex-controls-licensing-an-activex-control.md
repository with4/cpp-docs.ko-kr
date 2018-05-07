---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COleObjectFactory
dev_langs:
- C++
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 725e6cf167ec01635a3072f09ecaa2f5055b1891
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스
ActiveX 컨트롤의 선택적 기능 사용자 수를 사용 또는 컨트롤 배포를 제어 시스템 있습니다 수 라이센스 지원. (라이선스 문제에 대 한 자세한 논의 라이선스 문제에서을 참조 하십시오. [기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md).)  
  
 이 문서에서는 다음 내용을 다룹니다.  
  
-   [ActiveX 컨트롤 라이선스의 개요](#_core_overview_of_activex_control_licensing)  
  
-   [사용이 허가 된 컨트롤 만들기](#_core_creating_a_licensed_control)  
  
-   [라이선스 지원](#_core_licensing_support)  
  
-   [ActiveX 컨트롤의 라이선스를 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control)  
  
 ActiveX 컨트롤 라이선스를 구현 하는 다른 사용자는 ActiveX 컨트롤을 사용할 방법을 결정 하는 컨트롤 개발자로 사용 하면, 있습니다. 컨트롤에서 컨트롤 구매자에 게 제공 하 고 있습니다. 구매자에 게 컨트롤을 있지 않고 배포할 수 있습니다 규약과-사용권 계약 파일은 합니다. 컨트롤을 사용 하는 응용 프로그램 된-사용권 계약 파일입니다. 이렇게 하면 쓰기 첫 번째 라이선스를 제어 하지 않고 컨트롤을 사용 하는 새 응용 프로그램에서 해당 응용 프로그램의 사용자가 않습니다.  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> ActiveX 컨트롤 라이선스의 개요  
 ActiveX 컨트롤에 대 한 라이선스 지원을 제공 하는 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) 클래스의 여러 함수에 대 한 구현을 제공는 **IClassFactory2** 인터페이스: **IClassFactory2 :: RequestLicKey**, **IClassFactory2::GetLicInfo**, 및 **IClassFactory2::CreateInstanceLic**합니다. 컨테이너 응용 프로그램 개발자는 컨트롤에 대 한 호출의 인스턴스를 만드는 요청을 수행 하는 경우 `GetLicInfo` 되어 있는지 확인 하려고 하는 컨트롤입니다. -사용권 계약 파일은 있습니다. 컨트롤의 사용이 허가 되는 경우 컨트롤의 인스턴스를 생성 하 고 컨테이너에 배치 수 있습니다. 컨테이너 응용 프로그램 개발자가 완료 한 후 다른 함수 호출,이 이번에는 `RequestLicKey`, 이루어집니다. 이 함수는 컨테이너 응용 프로그램 라이선스 키 (단순한 문자 문자열)를 반환합니다. 그러면는 반환 된 값은 응용 프로그램에 포함 됩니다.  
  
 아래 그림에서는 ActiveX 컨트롤 컨테이너 응용 프로그램을 개발 하는 동안 사용 될 라이선스 확인을 보여 줍니다. 앞에서 설명한 대로 컨테이너 응용 프로그램 개발자는 적절 한이 있어야 합니다. 컨트롤의 인스턴스를 만들려면 개발 컴퓨터에 설치-사용권 계약 파일입니다.  
  
 ![사용이 허가 된 ActiveX 컨트롤이 개발 시 확인 됨](../mfc/media/vc374d1.gif "vc374d1")  
개발 도중 사용이 허가된 ActiveX 컨트롤 확인  
  
 다음 그림에 표시 된 다음 프로세스에는 최종 사용자는 컨테이너 응용 프로그램을 실행할 때 발생 합니다.  
  
 응용 프로그램이 시작 될 때 컨트롤의 인스턴스를 일반적으로 만들어야 합니다. 컨테이너를 호출 하 여이 수행 `CreateInstanceLic`, 포함 된 라이선스 키를 매개 변수로 전달 합니다. 그런 다음 포함 된 라이선스 키와 컨트롤의 고유 사본을 라이선스 키 간의 문자열 비교가 이루어집니다. 성공한 일치 하는 경우 컨트롤의 인스턴스를 만들 하 고 응용 프로그램이 계속 정상적으로 실행 합니다. 고 합니다. -사용권 계약 파일 컨트롤 사용자의 컴퓨터에 있는 수 있어야 합니다.  
  
 ![사용이 허가 된 ActiveX 컨트롤이 실행 시 확인 됨](../mfc/media/vc374d2.gif "vc374d2")  
실행 도중 사용이 허가된 ActiveX 컨트롤 확인  
  
 두 가지 기본 구성 요소로 이루어져 있습니다 컨트롤 라이선스: 컨트롤 구현 DLL에서에서 특정 코드 및 라이선스 파일입니다. 코드는 두 (세 개도 가능) 함수 호출 및 문자열을부터 "라이선스"를 포함 하는 문자열 저작권 표시 라고으로 구성 됩니다. 이 함수를이 호출 하 고 라이선스 문자열 컨트롤 구현에 있습니다 (합니다. Cpp) 합니다. ActiveX 컨트롤 마법사에 의해 생성 된 라이선스 파일은 저작권 문 사용 하 여 텍스트 파일. 프로젝트 이름에 사용 하 여 이름이 지정 됩니다는 합니다. 예를 들어 샘플-사용권 계약 확장입니다. -사용권 계약입니다. 디자인 타임 사용 하 여 필요 하지 않으면 라이센스가 있는 컨트롤 라이선스 파일이 포함 되어 있어야 합니다.  
  
##  <a name="_core_creating_a_licensed_control"></a> 사용이 허가 된 컨트롤 만들기  
 ActiveX 컨트롤 마법사를 사용 하 여 제어 프레임 워크를 만들 때 지원 라이선스를 포함 하기 쉽습니다. 컨트롤 런타임 라이선스를 포함 해야을 지정 하면 ActiveX 컨트롤 마법사 라이선스를 지원 하도록 컨트롤 클래스에 코드를 추가 합니다. 라이선스 확인에 대 한 키 및 라이선스 파일을 사용 하는 함수의 코드 구성 됩니다. 또한 이러한 함수는 컨트롤 라이선스를 사용자 지정 하려면 수정할 수 있습니다. 라이선스를 사용자 지정에 대 한 자세한 내용은 참조 하십시오. [ActiveX 컨트롤 라이선스를 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control) 이 문서의 뒷부분에 나오는 합니다.  
  
#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>컨트롤 프로젝트를 만들 때 ActiveX 컨트롤 마법사를 사용 하 여 라이센스에 대 한 지원을 추가 하려면  
  
1.  지침에 따라 [MFC ActiveX 컨트롤을 만드는](../mfc/reference/creating-an-mfc-activex-control.md)합니다. **응용 프로그램 설정** ActiveX 컨트롤 마법사의 페이지에는 런타임에 라이선스가 있는 컨트롤을 만들 수 있는 옵션이 포함 되어 있습니다.  
  
 ActiveX 컨트롤 마법사는 이제 기본 라이선스 지원을 포함 하는 ActiveX 컨트롤 프레임 워크를 생성 합니다. 라이선스 코드를 대 한 자세한 내용은 다음 항목을 참조 하십시오.  
  
##  <a name="_core_licensing_support"></a> 라이선스 지원  
 ActiveX 컨트롤 마법사에 ActiveX 컨트롤 라이센스 지원을 추가를 사용 하 여 ActiveX 컨트롤 마법사를 선언 하 고 기능을 구현 하는에 코드가 추가 컨트롤 헤더 파일과 구현 파일을 추가 합니다. 이 코드는 이루어져는 `VerifyUserLicense` 멤버 함수 및 `GetLicenseKey` 에 기본 구현 재정의 하는 멤버 함수를 [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) 합니다. 이러한 함수를 검색 하 고 컨트롤 라이선스를 확인 합니다.  
  
> [!NOTE]
>  세 번째 멤버 함수를 `VerifyLicenseKey` ActiveX 컨트롤 마법사에서 생성 되지 않습니다 되지만 라이선스 키 확인 동작을 사용자 지정을 재정의할 수 있습니다.  
  
 멤버 함수는:  
  
-   [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)  
  
     컨트롤 라이선스 파일의 존재 여부에 대 한 시스템을 확인 하 여 디자인 타임에 사용할 컨트롤을 허용 하는지 확인 합니다. 이 함수는 처리의 일부로 프레임 워크에서 호출 됩니다 **IClassFactory2::GetLicInfo** 및 **IClassFactory::CreateInstanceLic**합니다.  
  
-   [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)  
  
     컨트롤 DLL에서에서 고유 키를 요청합니다. 이 키는 컨테이너 응용 프로그램에 포함 되며 나중와 함께 사용할 `VerifyLicenseKey`, 컨트롤의 인스턴스를 만듭니다. 이 함수는 처리의 일부로 프레임 워크에서 호출 됩니다 **IClassFactory2::RequestLicKey**합니다.  
  
-   [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)  
  
     포함된 된 키와 컨트롤의 고유 키가 동일한 지 확인 합니다. 따라서 컨테이너를 사용에 대 한 컨트롤의 인스턴스를 만들 수 있습니다. 이 함수는 처리의 일부로 프레임 워크에서 호출 됩니다 **IClassFactory2::CreateInstanceLic** 라이선스 키의 사용자 지정된 확인 기능을 제공 하는 재정의 될 수 있습니다. 기본 구현은 문자열 비교를 수행 합니다. 자세한 내용은 참조 [ActiveX 컨트롤 라이선스를 사용자 지정](#_core_customizing_the_licensing_of_an_activex_control)이 문서의 뒷부분에 나오는 합니다.  
  
###  <a name="_core_header_file_modifications"></a> 헤더 파일 수정  
 ActiveX 컨트롤 마법사 컨트롤 헤더 파일에 다음 코드를 추가 합니다. 이 예제에서는 두 개의 멤버 함수에 `CSampleCtrl`개체의 `factory` 선언, 컨트롤의 현재 상태를 확인 하는 합니다. -사용권 계약 파일 및 다른 컨트롤이 포함 된 응용 프로그램에서 사용 될 라이선스 키를 검색 합니다.  
  
 [!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]  
  
###  <a name="_core_implementation_file_modifications"></a> 구현 파일 수정  
 라이선스 파일 이름 및 라이선스 문자열을 선언 하는 컨트롤 구현 파일에는 다음 두 문이 배치 하는 ActiveX 컨트롤 마법사:  
  
 [!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]  
  
> [!NOTE]
>  수정 하는 경우 **szLicString** 어떤 방식으로든에서 수정 해야 컨트롤의 첫 번째 줄. -사용권 계약 파일 또는 라이선스 제대로 작동 하지 않습니다.  
  
 컨트롤 클래스를 정의 하는 컨트롤 구현 파일에 다음 코드를 배치 하는 ActiveX 컨트롤 마법사 `VerifyUserLicense` 및 `GetLicenseKey` 함수:  
  
 [!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]  
  
 마지막으로 **ActiveX 컨트롤 마법사** 컨트롤 프로젝트를 수정 합니다. IDL 파일입니다. **사용이 허가 된** 키워드는 다음 예제와 같이 컨트롤의 coclass에 추가 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> ActiveX 컨트롤의 라이선스를 사용자 지정  
 때문에 `VerifyUserLicense`, `GetLicenseKey`, 및 `VerifyLicenseKey` 컨트롤 팩터리 클래스의 가상 멤버 함수로 선언 된 라이선스 컨트롤의 동작을 사용자 지정할 수 있습니다.  
  
 예를 들어 여러 수준의 재정의 하 여 컨트롤에 대 한 라이선스를 제공할 수 있습니다는 `VerifyUserLicense` 또는 `VerifyLicenseKey` 멤버 함수입니다. 이 함수에서는 속성 또는 메서드 검색 라이선스 등급에 따라 사용자에 게 노출 되 조정할 수 있습니다.  
  
 코드를 추가할 수도 있습니다는 `VerifyLicenseKey` 생성을 제어 하는 사용자에 게 알리는 실패에 대 한 사용자 지정 된 메서드를 제공 하는 함수입니다. 예를 들어 프로그램 `VerifyLicenseKey` 메시지를 표시할 수는 멤버 함수 상자 컨트롤을 초기화 하지 않는다는 및 이유입니다.  
  
> [!NOTE]
>  호출 하는 대신 특정 레지스트리 키에 대 한 등록 데이터베이스를 확인 하는 ActiveX 컨트롤 라이선스 확인을 사용자 지정 하는 다른 방법은 `AfxVerifyLicFile`합니다. 기본 구현 예 참조는 [구현 파일 수정](#_core_implementation_file_modifications) 이 문서의 섹션.  
  
 참조의 라이선스 문제에 대 한 자세한 내용은 라이선스 문제를 [기존 ActiveX 컨트롤 업그레이드](../mfc/upgrading-an-existing-activex-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)

