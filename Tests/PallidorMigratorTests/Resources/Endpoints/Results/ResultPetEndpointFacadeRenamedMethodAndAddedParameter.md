import Foundation
import Combine


public struct PetAPI {
    static let decoder : JSONDecoder = NetworkManager.decoder

    public static func addPet(status: String? , element: Pet , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<Pet, Error> {

return _PetAPI.addMyPet(status: status, element: element.to()!, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.map({Pet($0)!})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func deletePet(api_key: String? , petId: Int64 , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<String, Error> {

return _PetAPI.deletePet(api_key: api_key, petId: petId, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func findPetsByStatus(status: String? , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<[Pet], Error> {

return _PetAPI.findPetsByStatus(status: status, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.map({$0.map({Pet($0)!})})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func findPetsByTags(tags: [String]? , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<[Pet], Error> {

return _PetAPI.findPetsByTags(tags: tags, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.map({$0.map({Pet($0)!})})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func getPetById(petId: Int64 , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<Pet, Error> {

return _PetAPI.getPetById(petId: petId, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.map({Pet($0)!})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func updatePet(element: Pet , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<Pet, Error> {

return _PetAPI.updatePet(element: element.to()!, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.map({Pet($0)!})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func updatePetWithForm(petId: Int64 , name: String , status: String , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = NetworkManager.defaultContentType) -> AnyPublisher<String, Error> {

return _PetAPI.updatePetWithForm(petId: petId, name: name, status: status, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

public static func uploadFile(petId: Int64 , additionalMetadata: String? , element: String? , authorization: HTTPAuthorization  = NetworkManager.authorization!, contentType: String?  = "application/octet-stream") -> AnyPublisher<ApiResponse, Error> {

return _PetAPI.uploadFile(petId: petId, additionalMetadata: additionalMetadata, element: element, authorization: authorization, contentType: contentType)
.mapError({( OpenAPIError($0 as? _OpenAPIError)! )})
.map({ApiResponse($0)!})
.receive(on: DispatchQueue.main)
.eraseToAnyPublisher()
}

}
