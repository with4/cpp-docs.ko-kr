---
title: "이전 버전의 운영 체제의 CImage 제한 사항 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImage
dev_langs: C++
helpviewer_keywords: CImage class [MFC], limitations
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27046704975bf8f5e28f12acbfa72e860660fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-limitations-with-earlier-operating-systems"></a>이전 운영 체제의 CImage 제한 사항
많은 `CImage` 함수 최신 버전의 Windows에만 작동: Windows 95/98 또는 Windows NT 4.0 또는 Windows 2000입니다. 이 문서에서는 특정 메서드의 버전 제한 사항을 설명 합니다.  
  
 [CImage::PlgBlt](../atl-mfc-shared/reference/cimage-class.md#plgblt) 및 [CImage::MaskBlt](../atl-mfc-shared/reference/cimage-class.md#maskblt) 회사만 Windows NT 4.0 이상입니다. 이상 Windows 95/98에서 실행 되는 응용 프로그램에는 작동 하지 않습니다.  
  
 [CImage::AlphaBlend](../atl-mfc-shared/reference/cimage-class.md#alphablend) 및 [CImage::TransparentBlt](../atl-mfc-shared/reference/cimage-class.md#transparentblt) 이러한 메서드를 사용 하는 msimg32.lib 링크 해야 하기 때문에 이상만 Windows 2000 이상, Windows 98 작동 합니다. (이 라이브러리는 이상 Windows 2000 이상 및 Windows 98을 실행 하는 응용 프로그램에만 사용할 수 있습니다.)  
  
 포함할 수 있습니다 `AlphaBlend` 및 `TransparentBlt` 이러한 메서드 호출 되지 하는 경우에 Windows 95 나 Windows NT 4.0에서 실행 되는 응용 프로그램에 있습니다. 링커의를 사용 해야 응용 프로그램이 이러한 메서드를 포함 하는 경우 이전 버전의 운영 체제에서 실행 해야 [/delayload](../build/reference/delayload-delay-load-import.md) msimg32.lib의 로드를 지연 하 합니다. 응용 프로그램 Windows NT 4.0 또는 Windows 95에서 실행 되는 동안 다음이 방법 중 하나를 호출 하지 않습니다,으로 msimg32.lib 로드를 시도 하지 않습니다. 여부를 확인할 수 있습니다 투명도 지원을 사용할 수는 `CImage::IsTransparencySupported` 메서드.  
  
## <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 이러한 메서드를 호출 하는 응용 프로그램을 컴파일하려면 삽입 한 #define 하기 전에 _WIN32_WINNT 문을 # 버전의 Windows 5.0 임을 나타내는, 시스템 헤더를 including:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 사용 하지 않고 msimg32.lib에 직접 연결할 수 경우 응용 프로그램은 Windows 2000 또는 Windows 98 보다 오래 된 운영 체제에서 실행 하지 않아도, **/delayload**합니다.  
  
 [CImage::Draw](../atl-mfc-shared/reference/cimage-class.md#draw) Windows NT 4.0 또는 Windows 95와 사용 하지 않고 Windows 2000, Windows 98와 함께 사용할 때와 다르게 동작 합니다.  
  
 0x0500, 보다 작은 값으로 _WIN32_WINNT 설정 된 응용 프로그램을 컴파일하는 경우 **그리기** 는 하지만 작업을 처리 하지 것입니다 Windows 2000 및 Windows 98 이상 실행 하는 시스템에서 자동으로 투명 합니다.  
  
 프로그램 _WIN32_WINNT 0x0500로 설정 된 응용 프로그램이 나 큰를 컴파일하는 경우 **그리기** 투명도 Windows 2000 또는 Windows 98 이상 실행 하는 시스템에서 자동으로 처리 합니다. 에서도 작동 하지만 Windows NT 4.0 및 Windows 95; 투명도 지원 하지 않는 하지만 사용 해야 **/delayload** msimg32의 로드를 지연 하 합니다. LIB에 대해 위에서 설명한 것 처럼 `AlphaBlend` 및 `TransparentBlt`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImage 클래스](../atl-mfc-shared/reference/cimage-class.md)
