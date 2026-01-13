import React, { useState } from 'react';
import { Heart, Calendar, MapPin, CheckCircle, AlertCircle, Users, Droplet, ArrowRight, Menu, X, Info } from 'lucide-react';

// Componente de Navegación
const Navbar = () => {
    const [isOpen, setIsOpen] = useState(false);

    return (
        <nav className="bg-white shadow-md fixed w-full z-50">
            <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div className="flex justify-between h-20">
                    <div className="flex items-center">
                        <span className="flex items-center">
                            <Droplet className="h-8 w-8 text-[#c33042] mr-2" fill="#c33042" />
                            <div className="flex flex-col">
                                <span className="font-bold text-xl tracking-tight text-gray-900 uppercase">IES Arucas</span>
                                <span className="text-xs text-gray-500 font-semibold tracking-widest">DOMINGO RIVERO</span>
                            </div>
                        </span>
                    </div>
                    <div className="hidden md:flex items-center space-x-8">
                        <a href="#info" className="text-gray-700 hover:text-[#c33042] transition font-medium">Información</a>
                        <a href="#requisitos" className="text-gray-700 hover:text-[#c33042] transition font-medium">Requisitos</a>
                        <a href="#proceso" className="text-gray-700 hover:text-[#c33042] transition font-medium">El Proceso</a>
                        <a href="#registro" className="bg-[#c33042] text-white px-5 py-2 rounded-full font-bold hover:bg-[#a02030] transition shadow-lg transform hover:-translate-y-0.5">
                            Inscribirse
                        </a>
                    </div>
                    <div className="md:hidden flex items-center">
                        <button onClick={() => setIsOpen(!isOpen)} className="text-gray-700 hover:text-[#c33042] focus:outline-none">
                            {isOpen ? <X size={28} /> : <Menu size={28} />}
                        </button>
                    </div>
                </div>
            </div>
            {/* Menú Móvil */}
            {isOpen && (
                <div className="md:hidden bg-white border-t border-gray-100">
                    <div className="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                        <a href="#info" onClick={() => setIsOpen(false)} className="block px-3 py-2 text-base font-medium text-gray-700 hover:text-[#c33042] hover:bg-gray-50 rounded-md">Información</a>
                        <a href="#requisitos" onClick={() => setIsOpen(false)} className="block px-3 py-2 text-base font-medium text-gray-700 hover:text-[#c33042] hover:bg-gray-50 rounded-md">Requisitos</a>
                        <a href="#proceso" onClick={() => setIsOpen(false)} className="block px-3 py-2 text-base font-medium text-gray-700 hover:text-[#c33042] hover:bg-gray-50 rounded-md">El Proceso</a>
                        <a href="#registro" onClick={() => setIsOpen(false)} className="block px-3 py-2 text-base font-medium text-[#c33042] font-bold bg-red-50 rounded-md">Inscribirse Ahora</a>
                    </div>
                </div>
            )}
        </nav>
    );
};

// Sección Hero
const Hero = () => {
    return (
        <div className="relative bg-gray-900 overflow-hidden pt-20">
            <div className="absolute inset-0">
                {/* Abstract Background pattern */}
                <div className="absolute inset-0 bg-gradient-to-br from-gray-900 via-gray-800 to-black opacity-90"></div>
                <div className="absolute right-0 top-0 h-full w-1/2 bg-[#c33042] opacity-10 transform -skew-x-12 translate-x-20"></div>
            </div>
            <div className="relative max-w-7xl mx-auto py-24 px-4 sm:px-6 lg:px-8 flex flex-col items-center text-center sm:py-32">
                <span className="inline-flex items-center px-3 py-1 rounded-full text-sm font-semibold bg-red-900/30 text-red-100 border border-[#c33042] mb-6">
                    <Heart className="w-4 h-4 mr-2 text-[#c33042]" fill="#c33042" />
                    Comunidad Educativa IES Arucas
                </span>
                <h1 className="text-4xl font-extrabold tracking-tight text-white sm:text-5xl lg:text-6xl mb-6">
                    Tu sangre es vida.<br />
                    <span className="text-[#c33042]">Dónala con orgullo.</span>
                </h1>
                <p className="mt-4 text-xl text-gray-300 max-w-3xl mx-auto mb-10">
                    Profesores, alumnos y personal del Domingo Rivero: tenemos el poder de salvar vidas. Únete a nuestra jornada solidaria y conviértete en un héroe anónimo.
                </p>
                <div className="flex flex-col sm:flex-row gap-4">
                    <a href="#registro" className="inline-flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-[#c33042] hover:bg-[#a02030] md:py-4 md:text-lg md:px-10 transition shadow-lg shadow-red-900/50">
                        Quiero Donar
                    </a>
                    <a href="#info" className="inline-flex items-center justify-center px-8 py-3 border border-gray-500 text-base font-medium rounded-md text-gray-300 bg-transparent hover:bg-gray-800 md:py-4 md:text-lg md:px-10 transition">
                        Saber más
                    </a>
                </div>
            </div>
        </div>
    );
};

// Sección de Impacto y Estadísticas
const ImpactSection = () => {
    const features = [
        {
            icon: <Users className="h-8 w-8 text-white" />,
            title: "3 Vidas",
            desc: "Una sola donación puede salvar hasta tres vidas diferentes al separar los componentes sanguíneos."
        },
        {
            icon: <Droplet className="h-8 w-8 text-white" />,
            title: "20 Minutos",
            desc: "Es el tiempo que tardas en realizar el proceso completo. Un pequeño gesto, un impacto eterno."
        },
        {
            icon: <Heart className="h-8 w-8 text-white" />,
            title: "Solidaridad",
            desc: "Fomentamos los valores cívicos en nuestro centro. Es el mejor ejemplo que podemos dar."
        }
    ];

    return (
        <div id="info" className="py-16 bg-white">
            <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div className="text-center mb-16">
                    <h2 className="text-base text-[#c33042] font-semibold tracking-wide uppercase">La Importancia</h2>
                    <p className="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl">
                        ¿Por qué necesitamos tu ayuda?
                    </p>
                    <p className="mt-4 max-w-2xl text-xl text-gray-500 mx-auto">
                        Las reservas de sangre son vitales para cirugías, tratamientos oncológicos y emergencias. No se puede fabricar, solo se puede donar.
                    </p>
                </div>

                <div className="grid grid-cols-1 gap-8 md:grid-cols-3">
                    {features.map((feature, index) => (
                        <div key={index} className="relative group">
                            <div className="absolute -inset-0.5 bg-gradient-to-r from-gray-200 to-gray-100 rounded-lg blur opacity-50 group-hover:opacity-100 transition duration-200"></div>
                            <div className="relative p-6 bg-white ring-1 ring-gray-900/5 rounded-lg leading-none flex items-start space-x-6 h-full shadow-sm hover:shadow-md transition">
                                <div className="flex-shrink-0">
                                    <div className="flex items-center justify-center h-12 w-12 rounded-md bg-[#c33042] shadow-lg">
                                        {feature.icon}
                                    </div>
                                </div>
                                <div>
                                    <p className="text-lg font-bold text-gray-900 mb-2">{feature.title}</p>
                                    <p className="text-gray-600 leading-relaxed">
                                        {feature.desc}
                                    </p>
                                </div>
                            </div>
                        </div>
                    ))}
                </div>
            </div>
        </div>
    );
};

// Requisitos y Proceso (Diseño Dual)
const RequirementsAndProcess = () => {
    return (
        <div className="bg-gray-900 text-white py-20">
            <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                
                {/* Requisitos */}
                <div id="requisitos" className="mb-20">
                    <div className="lg:text-center mb-12">
                        <h2 className="text-3xl font-extrabold sm:text-4xl text-white">
                            ¿Quién puede <span className="text-[#c33042]">donar?</span>
                        </h2>
                        <p className="mt-4 max-w-2xl text-lg text-gray-400 lg:mx-auto">
                            La mayoría de las personas pueden donar sangre si tienen buena salud. Existen algunos requisitos básicos para garantizar la seguridad del donante y del receptor.
                        </p>
                    </div>
                    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                        {[
                            { title: "Edad", text: "Tener entre 18 y 65 años." },
                            { title: "Peso", text: "Pesar más de 50 kg." },
                            { title: "Salud", text: "Sentirse bien y no estar enfermo el día de la donación." },
                            { title: "Ayuno", text: "No venir en ayunas. Haber comido algo ligero." }
                        ].map((req, idx) => (
                            <div key={idx} className="bg-gray-800 p-6 rounded-xl border border-gray-700 hover:border-[#c33042] transition duration-300">
                                <CheckCircle className="w-8 h-8 text-[#c33042] mb-4" />
                                <h3 className="text-xl font-bold mb-2">{req.title}</h3>
                                <p className="text-gray-400">{req.text}</p>
                            </div>
                        ))}
                    </div>
                     <div className="mt-8 bg-gray-800/50 p-4 rounded-lg border-l-4 border-[#c33042] flex items-start">
                        <Info className="w-6 h-6 text-[#c33042] mr-3 flex-shrink-0 mt-0.5" />
                        <p className="text-sm text-gray-300">
                            <strong>Nota para alumnos:</strong> Si tienes 17 años, no podrás donar sangre todavía, pero puedes ayudar difundiendo el mensaje o como voluntario en la organización.
                        </p>
                    </div>
                </div>

                {/* Proceso */}
                <div id="proceso" className="border-t border-gray-800 pt-20">
                    <h2 className="text-3xl font-extrabold sm:text-4xl text-white mb-12 text-center">
                        El Proceso de Donación
                    </h2>
                    <div className="relative">
                        {/* Línea conectora (visible en desktop) */}
                        <div className="hidden md:block absolute top-1/2 left-0 w-full h-0.5 bg-gray-700 -translate-y-1/2 z-0"></div>
                        
                        <div className="relative z-10 grid grid-cols-1 md:grid-cols-4 gap-8">
                            {[
                                { step: "1", title: "Registro", text: "Rellena el formulario y pasa una breve entrevista médica confidencial." },
                                { step: "2", title: "Análisis", text: "Se realiza una pequeña prueba para verificar tu nivel de hemoglobina." },
                                { step: "3", title: "Donación", text: "La extracción dura entre 7 y 10 minutos. Se utiliza material estéril y de un solo uso." },
                                { step: "4", title: "Recuperación", text: "Descansa unos minutos y disfruta de un refrigerio para reponer fuerzas." }
                            ].map((item, idx) => (
                                <div key={idx} className="bg-gray-900 p-4 text-center">
                                    <div className="w-12 h-12 mx-auto bg-[#c33042] rounded-full flex items-center justify-center text-xl font-bold text-white mb-4 ring-4 ring-gray-900 relative">
                                        {item.step}
                                    </div>
                                    <h3 className="text-lg font-bold text-white mb-2">{item.title}</h3>
                                    <p className="text-sm text-gray-400">{item.text}</p>
                                </div>
                            ))}
                        </div>
                    </div>
                </div>

            </div>
        </div>
    );
};

// Formulario de Registro
const RegistrationForm = () => {
    const [result, setResult] = useState("");
    const [status, setStatus] = useState("idle"); // idle, sending, success, error

    const onSubmit = async (event) => {
        event.preventDefault();
        setStatus("sending");
        setResult("Enviando...");
        
        const formData = new FormData(event.target);
        formData.append("access_key", "cbc38aed-61b6-4814-848a-47026fcd6d68");

        try {
            const response = await fetch("https://api.web3forms.com/submit", {
                method: "POST",
                body: formData
            });

            const data = await response.json();

            if (data.success) {
                setResult("¡Formulario enviado con éxito! Gracias por tu solidaridad.");
                setStatus("success");
                event.target.reset();
            } else {
                console.log("Error", data);
                setResult(data.message);
                setStatus("error");
            }
        } catch (error) {
            console.error("Error de red", error);
            setResult("Ocurrió un error al enviar el formulario. Por favor, inténtalo de nuevo.");
            setStatus("error");
        }
    };

    return (
        <div id="registro" className="py-24 bg-gray-50">
            <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
                <div className="bg-white rounded-2xl shadow-xl overflow-hidden border border-gray-200">
                    <div className="md:flex">
                        <div className="md:w-1/2 bg-gray-900 p-10 text-white flex flex-col justify-center">
                            <h3 className="text-2xl font-bold mb-4">Confirma tu asistencia</h3>
                            <p className="text-gray-300 mb-8">
                                Para organizar mejor la jornada en el IES Arucas Domingo Rivero, necesitamos saber cuántas personas están dispuestas a participar.
                            </p>
                            <ul className="space-y-4">
                                <li className="flex items-center">
                                    <Calendar className="w-5 h-5 text-[#c33042] mr-3" />
                                    <span>Fecha pendiente de confirmación</span>
                                </li>
                                <li className="flex items-center">
                                    <MapPin className="w-5 h-5 text-[#c33042] mr-3" />
                                    <span>Salón de Actos / Gimnasio</span>
                                </li>
                                <li className="flex items-center">
                                    <AlertCircle className="w-5 h-5 text-[#c33042] mr-3" />
                                    <span>Recuerda traer tu DNI</span>
                                </li>
                            </ul>
                        </div>
                        <div className="md:w-1/2 p-10 bg-white">
                            {status === "success" ? (
                                <div className="h-full flex flex-col items-center justify-center text-center">
                                    <div className="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mb-4">
                                        <CheckCircle className="w-8 h-8 text-green-600" />
                                    </div>
                                    <h4 className="text-2xl font-bold text-gray-900 mb-2">¡Gracias!</h4>
                                    <p className="text-gray-600">{result}</p>
                                    <button 
                                        onClick={() => setStatus("idle")}
                                        className="mt-6 text-[#c33042] font-medium hover:underline"
                                    >
                                        Enviar otro registro
                                    </button>
                                </div>
                            ) : (
                                <form onSubmit={onSubmit} className="space-y-5">
                                    <input type="hidden" name="subject" value="Nuevo registro Donación Sangre - IES Arucas" />
                                    
                                    <div>
                                        <label htmlFor="name" className="block text-sm font-medium text-gray-700">Nombre Completo</label>
                                        <input type="text" name="name" required className="mt-1 block w-full px-3 py-2 bg-white border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-[#c33042] focus:border-[#c33042] sm:text-sm" placeholder="Tu nombre y apellidos" />
                                    </div>

                                    <div>
                                        <label htmlFor="role" className="block text-sm font-medium text-gray-700">Soy...</label>
                                        <select 
                                            name="role" 
                                            required 
                                            defaultValue="" 
                                            className="mt-1 block w-full px-3 py-2 bg-white border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-[#c33042] focus:border-[#c33042] sm:text-sm"
                                        >
                                            <option value="" disabled>Selecciona una opción</option>
                                            <option value="Profesor">Profesor/a</option>
                                            <option value="Alumno">Alumno/a</option>
                                            <option value="Personal No Docente">Personal No Docente</option>
                                            <option value="Otro">Otro</option>
                                        </select>
                                    </div>

                                    <div>
                                        <label htmlFor="age" className="block text-sm font-medium text-gray-700">Edad</label>
                                        <input type="number" name="age" min="16" max="99" required className="mt-1 block w-full px-3 py-2 bg-white border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-[#c33042] focus:border-[#c33042] sm:text-sm" placeholder="Años" />
                                    </div>

                                    <div className="flex items-start">
                                        <div className="flex items-center h-5">
                                            <input id="donate_intent" name="donate_intent" type="checkbox" className="focus:ring-[#c33042] h-4 w-4 text-[#c33042] border-gray-300 rounded" required />
                                        </div>
                                        <div className="ml-3 text-sm">
                                            <label htmlFor="donate_intent" className="font-medium text-gray-700">Intención de Donar</label>
                                            <p className="text-gray-500">Confirmo que tengo intención de asistir a la jornada para donar sangre.</p>
                                        </div>
                                    </div>

                                    <div>
                                        <button type="submit" disabled={status === "sending"} className="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-[#c33042] hover:bg-[#a02030] focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-[#c33042] disabled:opacity-50 transition">
                                            {status === "sending" ? "Enviando..." : "Confirmar Asistencia"}
                                        </button>
                                    </div>
                                    {status === "error" && <p className="text-red-500 text-sm mt-2">{result}</p>}
                                </form>
                            )}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    );
};

// Footer
const Footer = () => {
    return (
        <footer className="bg-black text-white">
            <div className="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8 border-b border-gray-800">
                <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div className="col-span-1">
                        <span className="flex items-center mb-4">
                            <Droplet className="h-6 w-6 text-[#c33042] mr-2" fill="#c33042" />
                            <span className="font-bold text-lg uppercase">IES Arucas Domingo Rivero</span>
                        </span>
                        <p className="text-gray-400 text-sm">
                            Comprometidos con la educación y los valores solidarios. Tu participación hace la diferencia.
                        </p>
                    </div>
                    <div className="col-span-1">
                        <h3 className="text-sm font-semibold text-gray-300 tracking-wider uppercase mb-4">Enlaces Rápidos</h3>
                        <ul className="space-y-2">
                            <li><a href="#" className="text-gray-400 hover:text-white transition">Inicio</a></li>
                            <li><a href="#info" className="text-gray-400 hover:text-white transition">Información</a></li>
                            <li><a href="#requisitos" className="text-gray-400 hover:text-white transition">Requisitos Médicos</a></li>
                        </ul>
                    </div>
                    <div className="col-span-1">
                        <h3 className="text-sm font-semibold text-gray-300 tracking-wider uppercase mb-4">Contacto</h3>
                        <p className="text-gray-400 text-sm mb-2">Camino de la Cruz, 22, 35400 Arucas, Las Palmas</p>
                        <p className="text-gray-400 text-sm">Teléfono: 928 60 11 20</p>
                    </div>
                </div>
            </div>
            <div className="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8 flex justify-between items-center">
                <p className="text-base text-gray-500">
                    &copy; 2024 IES Arucas Domingo Rivero. Todos los derechos reservados.
                </p>
            </div>
        </footer>
    );
};

// App Principal
const App = () => {
    return (
        <div className="min-h-screen bg-gray-50 text-gray-900 font-sans">
            <Navbar />
            <Hero />
            <ImpactSection />
            <RequirementsAndProcess />
            <RegistrationForm />
            <Footer />
        </div>
    );
};

export default App;
