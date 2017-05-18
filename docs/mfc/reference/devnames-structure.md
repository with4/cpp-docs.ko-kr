---
title: "DEVNAMES 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
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
ms.openlocfilehash: 698a338c94dfa402dd51fa4f683b92a5d30cc0cd
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="devnames-structure"></a>DEVNAMES 구조체
`DEVNAMES` 구조 드라이버, 장치 및 프린터에 대 한 출력 포트 이름을 식별 하는 문자열을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagDEVNAMES { /* dvnm */  
    WORD wDriverOffset;  
    WORD wDeviceOffset;  
    WORD wOutputOffset;  
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */  
} DEVNAMES;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *wDriverOffset*  
 (입/출력) 장치 드라이버의 파일 이름 (확장명 없음)를 포함 하는 null로 끝나는 문자열에 문자에서 오프셋을 지정 합니다. 입력에 대해 대화 상자에서 처음 표시 하려면 프린터를 확인 하는이 문자열이 사용 됩니다.  
  
 *wDeviceOffset*  
 (입/출력) Null로 끝나는 문자열에 (null을 포함 하는 32 바이트입니다 최대) 장치의 이름을 포함 하는 문자에서 오프셋을 지정 합니다. 이 문자열은 동일 해야는 **dmDeviceName** 의 멤버는 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) 구조입니다.  
  
 *wOutputOffset*  
 (입/출력) 실제 출력 매체 (출력 포트)에 대 한 DOS 장치 이름이 포함 된 null로 끝나는 문자열에 문자에서 오프셋을 지정 합니다.  
  
 *wDefault*  
 문자열에 포함 여부를 지정 된 `DEVNAMES` 구조는 기본 프린터를 식별 합니다. 이 문자열은 기본 프린터로 인쇄 마지막 작업 이후 변경 되지 않은 확인을 사용 합니다. 경우에는 입력된에 **DN_DEFAULTPRN** 플래그가 설정 된 다른 값는 `DEVNAMES` 구조는 현재 기본 프린터에 대해 확인 됩니다. 문자열 중 하나라도 일치 하지 않으면 문서를 재구성 해야 할 수 있는 사용자에 게 알려주는 경고 메시지가 표시 됩니다. 출력에는 **wDefault** 사용자 확인 단추를 선택 하 고 인쇄 설정 대화 상자가 표시 되었을 경우에 멤버를 변경 합니다. **DN_DEFAULTPRN** 기본 프린터를 선택한 경우 플래그가 설정 되어 있습니다. 특정 프린터를 선택한 경우에 플래그가 설정 되지 않았습니다. 이 멤버의 다른 모든 비트는 인쇄 대화 상자 프로시저가 내부 용도로 예약 되어 있습니다.  
  
## <a name="remarks"></a>주의  
 **PrintDlg** 함수 이러한 문자열을 사용 하 여 시스템에 정의 된 인쇄 대화 상자에서 멤버를 초기화 합니다. 사용자가 대화 상자를 닫으면 선택한 프린터에 대 한 정보는이 구조에 반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** commdlg.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)



