## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10 자동 등록 사용

자동 등록을 통해 사용자는 회사 또는 학교 계정을 추가하고 관리에 동의하여 회사 소유 또는 개인 Windows 10 PC 및 Intune의 Windows 10 Mobile 장치를 등록할 수 있습니다. 그 외에 사용자가 별도로 수행해야 하는 작업은 전혀 없습니다. 사용자 장치는 백그라운드에서 등록되어 Azure Active Directory에 가입됩니다. 등록된 장치는 Intune을 통해 관리됩니다.

**전제 조건**
- Azure Active Directory Premium 구독([평가판 구독](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune 구독


### <a name="configure-automatic-mdm-enrollment"></a>자동 MDM 등록 구성

1. [Azure 관리 포털](https://portal.azure.com)(https://manage.windowsazure.com)에 로그인하고 **Azure Active Directory**를 선택합니다.

  ![Azure Portal의 스크린샷](../media/auto-enroll-azure-main.png)

2. **이동성(MDM 및 MAM)**을 선택합니다.

  ![Azure Portal의 스크린샷](../media/auto-enroll-mdm.png)

3. **Microsoft Intune**을 선택합니다.

  ![Azure Portal의 스크린샷](../media/auto-enroll-intune.png)

4. 자동으로 등록할 사용자를 구성합니다.

  ![Azure Portal의 스크린샷](../media/auto-enroll-scope.png)

  다음 URL의 기본값을 사용합니다.
  - **MDM 등록**
  - **MDM 사용 약관**
  - **MDM 규정 준수**

5. Microsoft Intune에서 관리해야 하는 사용자의 장치를 지정합니다. 이러한 사용자의 Windows 10 장치는 Microsoft Intune을 사용한 관리에 자동으로 등록됩니다.

  - **모두**
  - **그룹**
  - **없음**

6. **저장**을 선택합니다.
