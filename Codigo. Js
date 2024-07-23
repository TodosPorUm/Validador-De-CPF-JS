 function validarCPF(cpf) {
    // Remove caracteres não numéricos
    cpf = cpf.replace(/[^\d]/g, '');

    // Verifica se o CPF tem 11 dígitos
    if (cpf.length !== 11) {
        return false;
    }

    // Verifica se todos os dígitos são iguais; ex: 000.000.000-00
    if (/^(\d)\1{10}$/.test(cpf)) {
        return false;
    }

    // Calcula o primeiro dígito verificador
    let soma = 0;
    for (let i = 0; i < 9; i++) {
        soma += parseInt(cpf.charAt(i)) * (10 - i);
    }
    let resto = 11 - (soma % 11);
    let digitoVerificador1 = resto === 10 || resto === 11 ? 0 : resto;

    // Verifica se o primeiro dígito verificador está correto
    if (digitoVerificador1 !== parseInt(cpf.charAt(9))) {
        return false;
    }

    // Calcula o segundo dígito verificador
    soma = 0;
    for (let i = 0; i < 10; i++) {
        soma += parseInt(cpf.charAt(i)) * (11 - i);
    }
    resto = 11 - (soma % 11);
    let digitoVerificador2 = resto === 10 || resto === 11 ? 0 : resto;

    // Verifica se o segundo dígito verificador está correto
    if (digitoVerificador2 !== parseInt(cpf.charAt(10))) {
        return false;
    }

    // CPF válido
    return true;
}

// Exemplos de uso:

let cpf1 = '123.456.789-09';
let cpf2 = '12345678909';

console.log(validarCPF(cpf1)); // true
console.log(validarCPF(cpf2)); // true
