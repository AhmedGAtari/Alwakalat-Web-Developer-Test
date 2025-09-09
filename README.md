# Alwakalat-Web-Developer-Test

We are looking for a frontend developer to complete a technical test. The goal is to build a responsive, user-friendly interface based on the provided design assets.

Requirements:
	1.	Technology Flexibility: You may use any frontend framework or library of your choice. The focus is on quality, responsiveness, and user experience.
	2.	Reactive & User-Friendly: The interface should be dynamic, intuitive, and responsive across devices.
	3.	Security Handling: Your implementation must handle standard security measures such as CSRF protection and API tokens.
	4.	Backend Communication: All communication with the backend should go through a frontend server (not directly from the browser to the API).
	5.	Design Implementation: The provided design images should be implemented accurately.

Evaluation Criteria:
	•	Code quality, readability, and maintainability
	•	Responsiveness and adherence to design
	•	Proper handling of API interactions and security
	•	Overall user experience and reactivity


Techniqual Instructions:
Design Page: Provided in the repo.
API URL: api.alwakalat.com

POST /admin/login

Request Body (JSON)
{
	emailAddress: String
	password: String
}

Response Body (JSON)
{
   	WAT: String
}



GET /admin/shops

Header
	<Authorization> : <WAT>

Response Body (JSON)
[
	uid: String
	joinDate: Long
	status: String
	accountType: AccountType
	emailAddress: String
	name: String
	phoneNumber: String
    address: String
    logo: Base64 String (PNG ONLY)
    location :{
		longitude: Double
		latitude: Double
	}
	socialMediaAccounts : [
    {
    platform: String
			accountLink: String
		}
	]
    public List<DiscountedService> discountedServices: [
		{
			id: String
			serviceName: String
			status: String
			originalPrice: Double
			discountPercent: Double
		}
	]
]



POST /admin/shops/create

Header
	<Authorization> : <WAT>

Request Body (JSON)
{
	emailAddress: String
	name: String
	phoneNumber: String
    address: String
    logo: Base64 String (PNG ONLY)
    location :{
		longitude: Double
		latitude: Double
	}
	socialMediaAccounts : [
		{
			platform: String (SocialMediaPlatform)
			accountLink: String
		}
	]
    public List<DiscountedService> discountedServices: [
		{
			id: String
			serviceName: String
			status: String
			originalPrice: Double
			discountPercent: Double
		}
	]
}

Response Body (JSON)
{
	uid: String
	joinDate: Long
	status: String
	accountType: AccountType
	emailAddress: String
	name: String
	phoneNumber: String
    address: String
    logo: Base64 String (PNG ONLY)
    location :{
		longitude: Double
		latitude: Double
	}
	socialMediaAccounts : [
		{
			platform: String
			accountLink: String
		}
	]
    public List<DiscountedService> discountedServices: [
		{
			id: String
			serviceName: String
			status: String
			originalPrice: Double
			discountPercent: Double
		}
	]
}



POST /admin/shops/update

Header
	<Authorization> : <WAT>

Request Body (JSON)
{
	uid: String
	emailAddress: String
	name: String
	phoneNumber: String
    address: String
    logo: Base64 String (PNG ONLY) (Nullable In Case No Logo Update)
    location :{
		longitude: Double
		latitude: Double
	}
	socialMediaAccounts : [
		{
			platform: String (SocialMediaPlatform)
			accountLink: String
		}
	]
    public List<DiscountedService> discountedServices: [
		{
			id: String
			serviceName: String
			status: String
			originalPrice: Double
			discountPercent: Double
		}
	]
}

Response Body (JSON)
{
	uid: String
	status: String
	emailAddress: String
	name: String
	phoneNumber: String
    address: String
    logo: Base64 String (PNG ONLY) (Nullable In Case No Logo Update)
    location :{
		longitude: Double
		latitude: Double
	}
	socialMediaAccounts : [
		{
			platform: String (SocialMediaPlatform)
			accountLink: String
		}
	]
    public List<DiscountedService> discountedServices: [
		{
			id: String
			serviceName: String
			status: String
			originalPrice: Double
			discountPercent: Double
		}
	]
}



SocialMediaPlatform {
    INSTAGRAM,
    FACEBOOK,
    TWITTER,
    SNAPCHAT,
    TIK_TOK,
    WHATS_APP
}

