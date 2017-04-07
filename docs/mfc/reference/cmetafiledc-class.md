---
title: "CMetaFileDC 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC class
- Windows metafiles [C++]
- metafiles, implementing
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4bff4d7601c4ffbc6fe5cbe73f5e057b79abf1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cmetafiledc-class"></a>CMetaFileDC 클래스
원하는 이미지 또는 텍스트를 만들기 위해 재생할 수 있는 GDI(그래픽 장치 인터페이스) 명령 시퀀스가 포함된 Windows 메타파일을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|`CMetaFileDC` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMetaFileDC::Close](#close)|장치 컨텍스트를 닫고 메타 파일의 핸들을 만듭니다.|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|확장 메타 파일 장치 컨텍스트를 닫고 확장 메타 파일 핸들을 만듭니다.|  
|[CMetaFileDC::Create](#create)|Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 `CMetaFileDC` 개체입니다.|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|향상 된 형식 메타 파일에 대 한 메타 파일 장치 컨텍스트를 만듭니다.|  
  
## <a name="remarks"></a>주의  
 Windows 메타 파일을 구현 하려면 먼저 작성 한 `CMetaFileDC` 개체입니다. 호출는 `CMetaFileDC` 생성자를 다음 호출에서 [만들기](#create) Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 멤버 함수는 `CMetaFileDC` 개체입니다.  
  
 다음 보내기는 `CMetaFileDC` 개체의 시퀀스 `CDC` GDI 명령을 재생 하기 위해. 와 같은 출력을 만들 수 있는 GDI 명령만 `MoveTo` 및 `LineTo`를 사용할 수 있습니다.  
  
 메타 파일에 원하는 명령을 보낸 후에 호출 된 **닫기** 메타 파일 장치 컨텍스트를 닫고 메타 파일 핸들을 반환 하는 멤버 함수입니다. 다음 삭제할는 `CMetaFileDC` 개체입니다.  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) 메타 파일 핸들 메타 파일을 반복 해 서 재생 하는 데 사용할 수 있습니다. 메타 파일 조작할 수도 있습니다 Windows 함수에서와 같은 [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)를 디스크에 메타 파일을 복사 하 합니다.  
  
 메타 파일은 더 이상 필요 없는 사용 하 여 메모리에서 삭제 된 [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows 함수입니다.  
  
 구현할 수도 있습니다는 `CMetaFileDC` 개체를 처리할 수 있도록 둘 다 호출 출력 GDI 호출을 같은 특성 `GetTextExtent`합니다. 이러한 메타 파일은 보다 유연 하 고 더 쉽게 다시 사용할 수 종종 출력 및 특성에 대 한 호출의 조합으로 구성 된 일반 GDI 코드입니다. `CMetaFileDC` 클래스 두 개의 장치 컨텍스트를 상속 `m_hDC` 및 `m_hAttribDC`에서 `CDC`합니다. `m_hDC` 장치 컨텍스트는 모든 처리 [CDC](../../mfc/reference/cdc-class.md) GDI 출력 호출 및 `m_hAttribDC` 장치 컨텍스트는 모든 처리 `CDC` GDI 특성 호출 합니다. 일반적으로 이러한 두 개의 장치 컨텍스트는 동일한 장치를 참조 하십시오. 경우 `CMetaFileDC`, 특성이 DC로 설정 된 **NULL** 기본적으로 합니다.  
  
 화면, 프린터 또는 장치 이외의 메타 파일을 가리키는 호출 하는 두 번째 장치 컨텍스트는 `SetAttribDC` 멤버 함수에서 새 장치 컨텍스트를 연결 하려면 `m_hAttribDC`합니다. 정보에 대 한 GDI 호출 리디렉션됩니다 새 `m_hAttribDC`합니다. 출력 GDI 호출 들어가는지 `m_hDC`, 메타 파일을 나타냅니다.  
  
 대 한 자세한 내용은 `CMetaFileDC`, 참조 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="close"></a>CMetaFileDC::Close  
 메타 파일 장치 컨텍스트를 닫고 메타 파일을 사용 하 여 재생에 사용할 수 있는 Windows 메타 파일 핸들을 만듭니다는 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) 멤버 함수입니다.  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>반환 값  
 유효한 **HMETAFILE** 함수는 성공 하 고, 그렇지 않으면 경우 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 와 같은 Windows 함수와 함께 메타 파일을 조작 하는 Windows 메타 파일 핸들 사용할 수도 있습니다 [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480)합니다.  
  
 Windows를 호출 하 여 메타 파일 사용 후 삭제 [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) 함수입니다.  
  
##  <a name="closeenhanced"></a>CMetaFileDC::CloseEnhanced  
 확장 메타 파일 장치 컨텍스트를 닫고 확장 형식 메타 파일을 식별 하는 핸들을 반환 합니다.  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>반환 값  
 확장된 메타 파일, 성공 하는 경우의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램이 함수에 의해 반환 되는 확장 메타 파일 핸들을 사용 하 여 다음 작업을 수행할 수 있습니다.  
  
-   메타 파일에 저장 된 그림 표시  
  
-   확장된 메타 파일의 복사본 만들기  
  
-   열거, 편집 또는 개별 레코드 확장된 메타 파일에 복사 합니다.  
  
-   확장 메타 파일 헤더에서 메타 파일 내용에 대 한 설명을 검색합니다  
  
-   확장 메타 파일 헤더의 복사본을 검색  
  
-   확장된 메타 파일의 복사본을 이진 검색  
  
-   선택적인 색상표의 색을 열거  
  
-   향상 된 형식 메타 파일을 Windows 형식의 메타 파일로 변환  
  
 Win32 호출 하 여 핸들을 해제 해야 응용 프로그램이 더 이상 필요 없는 확장된 메타 파일 핸들 때 **DeleteEnhMetaFile** 함수입니다.  
  
##  <a name="cmetafiledc"></a>CMetaFileDC::CMetaFileDC  
 생성 한 `CMetaFileDC` 두 단계에서는 개체입니다.  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>주의  
 첫째, 호출 `CMetaFileDC`, 다음 호출 **만들기**, Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 `CMetaFileDC` 개체입니다.  
  
##  <a name="create"></a>CMetaFileDC::Create  
 생성 한 `CMetaFileDC` 두 단계에서는 개체입니다.  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszFilename*  
 Null로 끝나는 문자열을 가리킵니다. 만들려는 메타 파일의 파일 이름을 지정 합니다. 경우 *lpszFilename* 는 **NULL**, 새로운 메모리 내 메타 파일 생성 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 먼저 생성자를 호출 `CMetaFileDC`, 다음 호출 **만들기**, Windows 메타 파일 장치 컨텍스트를 만들고 연결 하는 `CMetaFileDC` 개체입니다.  
  
##  <a name="createenhanced"></a>CMetaFileDC::CreateEnhanced  
 향상 된 형식 메타 파일에 대 한 장치 컨텍스트를 만듭니다.  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDCRef`  
 확장된 메타 파일에 대 한 참조 장치를 식별합니다.  
  
 `lpszFileName`  
 Null로 끝나는 문자열을 가리킵니다. 만들려는 확장된 메타 파일의 파일 이름을 지정 합니다. 이 매개 변수가 **NULL**, 확장된 메타 파일 메모리 기반 이며 때나는 개체가 소멸 될 때 손실 내용이 Win32 **DeleteEnhMetaFile** 함수를 호출 합니다.  
  
 `lpBounds`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 데이터 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체의 크기를 지정 하는 **HIMETRIC** 확장된 메타 파일에 저장 되는 그림의 단위 (.01 밀리미터 단위로 증가).  
  
 `lpszDescription`  
 그림의 제목 뿐만 아니라 그림을 만든 응용 프로그램의 이름을 지정 하는&0;으로 끝나는 문자열을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 확장된 메타 성공 하면이 파일에 대 한 장치 컨텍스트 핸들을 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 장치 독립적 사진을 저장 하이 DC는 사용할 수 있습니다.  
  
 Windows로 식별 되는 참조 장치를 사용 하 여는 `pDCRef` 매개 변수 해상도 장치에 그림을 원래 표시의 단위를 기록 합니다. 하는 경우는 `pDCRef` 매개 변수는 **NULL**, 현재 디스플레이 장치를 사용 하 여 참조 합니다.  
  
 왼쪽 및 위쪽 멤버는 `RECT` 가리키는 데이터 구조는 `lpBounds` 매개 변수 각각 오른쪽 및 아래쪽 구성원 미만 이어야 합니다. 사각형의 가장자리를 따라 포인트는 그림에 포함 됩니다. 경우 `lpBounds` 는 **NULL**, 그래픽 장치 인터페이스 (GDI) 응용 프로그램에서 그림을 묶을 수 있는 가장 작은 사각형의 크기를 계산 합니다. `lpBounds` 가능한 경우 매개 변수를 제공 해야 합니다.  
  
 가리키는 문자열은 `lpszDescription` 매개 변수는 응용 프로그램 이름 및 그림 이름 사이는 null 문자를 포함 해야 하 고 두 null 문자로 끝나야-예를 들어 "XYZ 그래픽 Editor\0Bald Eagle\0\0," 여기서 \0 null 문자를 나타냅니다. 경우 `lpszDescription` 는 **NULL**, 확장 메타 파일 헤더에 해당 항목이 없습니다.  
  
 이 함수에 의해 생성 되는 DC를 사용 하 여 확장된 메타 파일에 그래픽 그림을 저장 하는 응용 프로그램. 이 DC를 식별 하는 핸들 GDI 함수에 전달할 수 있습니다.  
  
 모든 출력 장치에서 호출 하 여 그림을 표시할 수 그림 확장된 메타 파일에 저장 하는 응용 프로그램, 후는 `CDC::PlayMetaFile` 함수입니다. Windows에서 가리키는 사각형 그림을 표시할 때 사용 된 `lpBounds` 매개 변수 및 배치 하 고 그림의 크기를 조정 하는 참조 장치에서 해결 데이터. 이 함수에서 반환 하는 장치 컨텍스트는 모든 새 DC와 관련 된 동일한 기본 특성을 포함 합니다.  
  
 응용 프로그램에서 Win32를 사용 해야 **GetWinMetaFileBits** 확장된 메타 파일에서 이전 Windows 메타 파일 형식으로 변환 하는 함수입니다.  
  
 확장된 메타 파일의 파일 이름을 사용 해야는 합니다. EMF 확장입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




