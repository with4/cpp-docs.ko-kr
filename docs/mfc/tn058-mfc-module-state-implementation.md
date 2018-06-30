---
title: 'TN058: MFC 모듈 상태 구현 | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.implementation
dev_langs:
- C++
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 662ac381fe5513747795f38866172e6dea6fdb03
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121993"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC 모듈 상태 구현

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 기술 노트 "모듈 상태" MFC 구문 구현에 설명 합니다. MFC를 사용 하 여 DLL에서 Dll을 공유에 대 한 모듈 상태 구현에 대 한 이해가 중요는 (또는 종속 프로세스 OLE 서버).

이 노트를 읽기 전에 "관리는 데이터의 MFC 모듈 상태"에서 참조 [새 문서 만들기, 창 및 뷰](../mfc/creating-new-documents-windows-and-views.md)합니다. 이 문서는 중요 한 사용 정보 및이 주제에 대 한 개요 정보를 포함합니다.

## <a name="overview"></a>개요

MFC 상태 정보의 세 종류: 모듈 상태, 프로세스 상태 및 스레드 상태입니다. 경우에 따라 이러한 상태 형식은 결합할 수 있습니다. 예를 들어, MFC의 핸들 지도 로컬 모듈와 스레드 로컬입니다. 이렇게 하면 두 개의 다른 모듈에서 각 해당 스레드 지도 포함 하도록 합니다.

프로세스 상태 및 스레드 상태는 유사 합니다. 이러한 데이터 항목은 것은 전역 변수 전통적 하지만 지정된 된 프로세스에 따라 달라질 하거나 적절 한 Win32s를 지원 하는지 또는 적절 한 다중 스레딩을 지원에 대 한 스레드 해야 할 것입니다. 지정 된 데이터 항목에 어떻게 맞추는 범주 해당 항목 및 프로세스 및 스레드 경계와 관련 하 여 필요한 의미 체계에 따라 달라 집니다.

모듈 상태는 글로벌 상태 또는 로컬 프로세스 또는 스레드 로컬 상태 중 하나를 포함할 수 있다는 점에서 고유 합니다. 또한 것 빠르게 전환 될 수 있습니다.

## <a name="module-state-switching"></a>모듈 상태 전환

"Active" 또는 "현재" 모듈 상태에 대 한 포인터를 포함 하는 각 스레드 (레지스터 포인터는 MFC의 스레드 로컬 상태의 일부임). 이 포인터는 스레드 실행 OLE 컨트롤 또는 DLL 또는 OLE 컨트롤에 다시 전화 응용 프로그램을 호출 하는 응용 프로그램과 같이 모듈 경계에 전달 될 때 변경 됩니다.

호출 하 여 현재 모듈 상태 전환 될 `AfxSetModuleState`합니다. 대부분의 경우 API를 사용 하 여 직접 있습니다이 처리 하는 것은 하지 않습니다. MFC, 대부분의 경우에서는 호출 수 (WinMain, OLE 시작 지점에서 `AfxWndProc`등.). 특별 한에 정적으로 연결 하 여 작성 하는 구성 요소에서 이렇게 `WndProc`, 및 특수 한 `WinMain` (또는 `DllMain`) 모듈 상태를 현재 해야 알고 있는 합니다. DLLMODUL 확인 하 여이 코드를 볼 수 있습니다. CPP 또는 APPMODUL 합니다. CPP MFC\SRC 디렉터리에 있습니다.

거의 되도록 모듈 상태를 설정 하 고 다음 하지 다시 설정 합니다. 대부분의 경우 "push" 자체적으로 모듈을 현재 하 고을 완료 한 후 "pop" 원래 컨텍스트로 다시 합니다. 매크로 의해 이렇게 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) 및 특수 클래스 `AFX_MAINTAIN_STATE`합니다.

`CCmdTarget` 모듈 상태 전환 지원 하기 위한 특수 기능에 있습니다. 특히, 한 `CCmdTarget` 진입점 OLE COM 및 OLE 자동화에 사용 된 루트 클래스입니다. 마찬가지로 다른 진입점을 시스템에 노출 이러한 진입점에서 올바른 모듈 상태 설정 해야 합니다. 어떻게 않습니다는 주어진 `CCmdTarget` 보유 "올바른" 모듈 상태 해야 "를 기억 하 여" "현재" 모듈 상태 이란 생성 될 때, 설정할 수 있도록 하는 현재 모듈 상태 "기억" 이후 때 값이 호출에 대 한 대답은 알고 합니다. 결과적으로 모듈을 사용 함을 제시는 주어진 `CCmdTarget` 개체가 연결 된와 현재 개체를 생성 하는 경우의 모듈 상태입니다. INPROC 서버 로드, 개체 생성 및 해당 메서드 호출의 간단한 예를 수행 합니다.

1.  OLE에서 DLL이 로드를 사용 하 여 `LoadLibrary`합니다.

2. `RawDllMain` 먼저 호출 됩니다. DLL에 대 한 모듈 상태 정적 모듈을 알려진된 상태로 설정합니다. 이러한 이유로 `RawDllMain` DLL에 정적으로 연결 됩니다.

3.  이 개체와 관련 된 클래스 팩터리에 대 한 생성자를 호출 합니다. `COleObjectFactory` 파생 된 `CCmdTarget` 어떤 모듈 상태의 인스턴스화할 기억 결과적으로, 하 고 있습니다. 이 중요-개체를 만드는 클래스 팩터리 물으면 알고 이제 현재 레코드로 모듈 상태입니다.

4. `DllGetClassObject` 클래스 팩터리를 가져오는 위해 호출 됩니다. MFC는이 모듈에 연결 된 클래스 팩터리 목록을 검색 하 고 반환 합니다.

5. `COleObjectFactory::XClassFactory2::CreateInstance`가 호출된 경우 모듈 상태 3 단계에서 현재 모듈 상태를이 함수는 개체를 만들고 반환 하기 전에 설정 (된 현재 시기는 `COleObjectFactory` 인스턴스화한). 내부에 이렇게 [METHOD_PROLOGUE](com-interface-entry-points.md)합니다.

6.  너무은 개체가 만들어질 때는 `CCmdTarget` 파생와 같은 방식으로 `COleObjectFactory` 는 모듈 상태, 활성 상태 였던 기억 사라지면이 새 개체입니다. 로 전환 하는 모듈 상태를 알고 이제 때마다 호출 됩니다.

7.  클라이언트에서 받은 OLE COM 개체에는 함수를 호출 합니다. 해당 `CoCreateInstance` 호출 합니다. 사용 하 여 해당 개체를 호출 하는 경우 `METHOD_PROLOGUE` 모듈 상태와 동일 하 게 전환할 `COleObjectFactory` 않습니다.

볼 수 있듯이 메시지 만들어질 때 개체에 개체에서 모듈 상태 전파 됩니다. 모듈 상태가 적절 하 게 설정 하는 것이 유용 합니다. 설정 되지 않은 경우 DLL 또는 COM 개체 수와 상호 작용 불완전 하 게 호출 하 고 또는 자체 리소스를 찾을 수 없습니다 또는 불쾌 한 다른 방법으로 실패할 수 있습니다 하는 MFC 응용 프로그램.

특정 종류의 Dll, 특히 "MFC 확장" Dll의 모듈 상태를 전환 하지 마십시오 참고 자신의 `RawDllMain` (실제로, 일반적으로 없는 경우는 `RawDllMain`). 즉, "것 처럼 작동"은 실제로 사용 하 여 응용 프로그램에 존재 하는 데 사용 됩니다. 실행 중인 응용 프로그램의 일부 거의 아니며 해당 의도를 해당 응용 프로그램의 글로벌 상태를 수정 합니다.

OLE 컨트롤 및 기타 Dll은 매우 다릅니다. 호출 응용 프로그램의 상태를 수정 하려면 원하지 않습니다 호출 하는 응용 프로그램이 MFC 응용 프로그램에 아닐 수도 있고 없으므로 수정할 수 없는 상태 수 있습니다. 모듈 상태 전환 고안 된 이유입니다.

사용자 DLL에 대화 상자를 시작 하는 것과 같은 DLL에서 내보낸된 함수에 대 한 함수 시작 부분에 다음 코드를 추가 해야 합니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

반환 된 상태와 현재 모듈 상태 서로 바뀝니다 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) 현재 범위의 끝까지 합니다.

AFX_MODULE_STATE 매크로 사용 하지 않는 경우 리소스 Dll에서 문제가 발생 합니다. 기본적으로 MFC 리소스 템플릿을 로드 하는 주 응용 프로그램의 리소스 핸들을 사용 합니다. 이 서식 파일은 실제로 DLL에 저장 됩니다. 근본 원인을 AFX_MODULE_STATE 매크로 의해 MFC의 모듈 상태 정보는 되지 전환입니다. 리소스 핸들 MFC 모듈 상태에서 복구 됩니다. 모듈 상태를 전환 하지 않으면 잘못 리소스 핸들을 사용 하면 됩니다.

AFX_MODULE_STATE는 DLL에 있는 모든 함수에 지정할 필요는 없습니다. 예를 들어 `InitInstance` MFC 모듈 상태 하기 전에 자동으로 이동 하기 때문에 AFX_MODULE_STATE 없이 응용 프로그램에는 MFC 코드에서 호출할 수 있습니다 `InitInstance` 및 후에 백업 하는 스위치 다음 `InitInstance` 반환 합니다. 모든 메시지 맵 처리기에도 마찬가지입니다. 일반 MFC Dll에는 실제로 메시지를 라우팅하기 전에 모듈 상태를 자동으로 전환 하는 특수 한 마스터 창 프로시저 있는데

## <a name="process-local-data"></a>로컬 데이터 처리

로컬 데이터 처리는 이러한 크게 문제가 수 없습니다 것 되지 않은 Win32s DLL 모델의 어려움에 대 한. W i n 32에서 여러 응용 프로그램에서 로드 하는 경우에 모든 Dll의 글로벌 데이터를 공유 합니다. 이 각 DLL의 DLL에 연결 하는 각 프로세스에서 데이터 공간을 별도 복사본을 가져옵니다 "실제" Win32 DLL 데이터 모델에서 매우 다릅니다. 복잡성을 추가 하려면 Win32s DLL에 힙에 할당 된 데이터는 실제로 프로세스 특정 (적어도 오래 되는 소유권 만큼). 다음 데이터와 코드를 고려 합니다.

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

위의 코드에 있는 경우 DLL에 A와 B (, 실제로 수도 동일한 응용 프로그램의 두 인스턴스)의 두 프로세스에 의해 DLL이 로드 되 고 어떤 일이 생기는 것이 좋습니다. 호출 `SetGlobalString("Hello from A")`합니다. 에 대 한 메모리를 할당 하는 결과적으로,는 `CString` A.에 유지 하는 프로세스의 컨텍스트에서 데이터 다음에 유의 `CString` 자체 전역 표시 되 고 두 a와 B 이제 B 호출 `GetGlobalString(sz, sizeof(sz))`합니다. B A 설정 하는 데이터를 볼 수 있습니다. 즉, Win32s 제공 Win32 같이 프로세스 간에 보호 되지 않습니다. 즉 첫 번째 문제는; 대부분의 경우에서은 응용 프로그램이 다른 응용 프로그램을 소유할 수로 간주 되는 전역 데이터에 영향을 두 개에 바람직하지 않습니다.

추가 문제에도 있습니다. 이제 종료 될 경우를 가정해 봅니다. 때 A 종료 되 면 사용 되는 메모리는 '`strGlobal`' 문자열 데 사용할 수 있는 시스템-즉, 프로세스 A가 할당 한 모든 메모리 운영 체제에 의해 자동으로 해제 됩니다. 때문에 해제 되지 않습니다는 `CString` 소멸자가 호출 되 고, 아직 호출 되지 않았습니다. 단순히 해제 장면 남아 서 할당 된 후 응용 프로그램 때문에 있습니다. B 라는 이제 `GetGlobalString(sz, sizeof(sz))`, 유효한 데이터를 가져올 수 있습니다. 다른 응용 프로그램 일부는 다른 작업에 대 한 메모리를 사용 되었습니다.

명확 하 게에 문제가 있습니다. MFC 3.x 스레드 로컬 저장소 (TLS) 이라는 기술을 사용 합니다. MFC 3.x 하는 호출 되지 않습니다 하는 경우에 w i n 32에서 실제로 역할을 하는 프로세스 로컬 저장소 인덱스 TLS 인덱스 할당 하 고 다음 해당 TLS 인덱스를 기반으로 하는 모든 데이터를 참조 합니다. 이 Win32에 스레드 로컬 데이터를 저장 하는 데 사용 된 TLS 인덱스 비슷합니다 (해당 주제에 대 한 자세한 내용은 아래 참조). 이 프로세스 마다 두 개 이상의 TLS 인덱스를 활용 하는 모든 MFC DLL 발생 합니다. OLE 컨트롤의 Dll (Ocx)를 로드 하기 위한 계정 신속 하 게 실행 하면 TLS 인덱스 (개가 64) 부족 합니다. 또한 MFC는 단일 구조에의 한 곳에서이 모든 데이터를 저장 했습니다. 확장성이 크지는 없습니다 하 고 TLS 인덱스의 사용을 고려 하 여 이상적인 없습니다.

MFC 4.x 이러한 측면을 래핑할 수 있습니다"" 로컬 프로세스 되어야 하는 데이터에 대 한 클래스 템플릿 집합이 함께 다룹니다. 예를 들어, 작성 하 여 위에서 언급 한 문제를 해결할 수 있습니다.

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC는 두 단계로이 구현 합니다. 첫째,은 Win32 위의 계층으로 __Tls\*__  Api (**TlsAlloc**, **TlsSetValue**, **TlsGetValue**등)는 두 개의 TLS 인덱스 프로세스당 있는 Dll에 관계 없이 사용 됩니다. 두 번째는 `CProcessLocal` 템플릿을이 데이터에 액세스 하기 위해 제공 됩니다. 연산자를 재정의 하는 것은 위에서 참조 하는 직관적인 구문을 할 수-> 합니다. 로 래핑된 개체를 모두 `CProcessLocal` 에서 파생 되어야 합니다 `CNoTrackObject`합니다. `CNoTrackObject` 하위 수준 할당자를 제공 (**LocalAlloc**/**LocalFree**)와 가상 소멸자는 프로세스가 종료 될 때 MFC 로컬 개체 처리를 자동으로 제거할 수 있도록 합니다. 이러한 개체는 추가 정리 해야 하는 경우 사용자 정의 소멸자를 사용할 수 있습니다. 위의 예제에서는 컴파일러에서 제거할 포함 된 기본 소멸자를 생성 하므로, 필요 하지 않습니다 `CString` 개체입니다.

이 방법에 관심 있는 다른 장점이 있습니다. 뿐만 아니라는 모두 `CProcessLocal` 개체 소멸을 자동으로 필요할 때까지 생성 되지 않은 됩니다. `CProcessLocal::operator->` 연결된 된 개체가 처음으로 호출 되 고 즉시 인스턴스화입니다. 따라서 위의 예제에는 '`strGlobal`' 문자열 처음까지 생성 되지 것입니다 `SetGlobalString` 또는 `GetGlobalString` 라고 합니다. 경우에 따라 DLL 시작 시간을 절약할 수 있습니다이 있습니다.

## <a name="thread-local-data"></a>스레드 로컬 데이터

로컬 데이터를 처리 하는 마찬가지로 스레드 로컬 데이터 때 사용 됩니다 데이터는 지정 된 스레드에 대해 로컬 이어야 합니다. 즉, 해당 데이터에 액세스 하는 각 스레드에 대 한 데이터의 개별 인스턴스가 필요 합니다. 이 여러 번 사용할 수 있습니다 광범위 한 동기화 메커니즘 대신이 대화 상자. 데이터는 다중 스레드에서 공유 필요가 없는 경우 비용이 많이 들고 불필요 한 메커니즘이 수 있습니다. 가정해는 `CString` 개체 (위의 예제 처럼). 에서는 스레드 로컬 하 여 만들 수와 묶어서는 `CThreadLocal` 템플릿:

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

경우 `MakeRandomString` 호출 된 두 개의 서로 다른 스레드에서 각는 "순서 섞기를" 문자열 다른 방법으로 서로 방해 하지 않고 있습니다. 이 있기 때문에 실제로 `strThread` 인스턴스 하나만 전역 인스턴스 대신 스레드당 합니다.

참고 방법을 대 한 참조를 캡처하는 사용 되는 `CString` 주소 한 번 대신 한 번 루프 반복 마다. 루프 코드와 작성 된 `threadData->strThread` everywhere '`str`'을 사용 하는 유효 하지만 코드는 훨씬 느리게 실행 됩니다. 이러한 참조는 루프에서 발생 하는 경우 데이터에 대 한 참조를 캐시 하는 것이 좋습니다.

`CThreadLocal` 클래스 템플릿에서 동일한 메커니즘을 사용 하는 `CProcessLocal` 는 않으며 동일한 기술을 구현 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)  
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)  
