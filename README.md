# Projet RecaptchaNet Implementation - WebForm C# 4.7.2

## Une intégration de RecaptchaNet dans un projet WebForm développé en C# 4.7.2. 

### Configuration requise :

1. .NET Framework 4.7.2

2. Clé API reCAPTCHA (obtenue sur Google reCAPTCHA)

3. Installation

### Clonez le référentiel dans votre environnement de développement local.
      
      git clone https://github.com/votre-utilisateur/RecaptchaNet-WebForm
      
### Ouvrez le projet dans Visual Studio.

#### Configurez votre clé API reCAPTCHA dans le fichier Web.config.
          
          <appSettings>
            <add key="RecaptchaSiteKey" value="VOTRE_CLE_SITE_RECAPTCHA" />
            <add key="RecaptchaSecretKey" value="VOTRE_CLE_SECRETE_RECAPTCHA" />
          </appSettings>

### Compilez et exécutez le projet.

### Ajoutez le contrôle RecaptchaNet à vos pages WebForm.


        <%@ Register Assembly="Recaptcha.Web" Namespace="Recaptcha.Web.UI.Controls" TagPrefix="cc1" %>
        ...
        <%-- Ajoutez le contrôle RecaptchaWidget dans votre formulaire --%>
        <cc1:RecaptchaWidget ID="Recaptcha1" runat="server" />


#### Validez la réponse du reCAPTCHA dans le code-behind.

        
        // Méthode déclenchée lors du clic sur le bouton "Valider"
        protected void btnValider_Click(object sender, EventArgs e)
        {
            // Vérifie si la réponse du reCAPTCHA est vide ou nulle
            if (String.IsNullOrEmpty(Recaptcha1.Response))
            {
            // La réponse du reCAPTCHA est manquante, traiter ce cas si nécessaire
            }
           else
           {
            // La réponse du reCAPTCHA est présente, procéder à la vérification
            var result = Recaptcha1.Verify();

            // Vérifie si la vérification du reCAPTCHA a réussi
            if (result.Success)
            {
            // La vérification du reCAPTCHA a réussi, traiter ce cas si nécessaire
            }
            else
            {
            // La vérification du reCAPTCHA a échoué, traiter ce cas si nécessaire
            }
          }
      }

N'oubliez pas de consulter la documentation de RecaptchaNet pour plus d'informations sur la configuration avancée et d'autres fonctionnalités.






