# slugfy-retirar-caracteres-especiais
Retira os caracteres especiais em JS

//Function SlugFy

function slugify(str) {

      // Converte o texto para caixa baixa:
      str = str.toLowerCase();

      // Remove qualquer caractere em branco do final do texto:
      str = str.replace(/^\s+|\s+$/g, '');

      // Lista de caracteres especiais que serão substituídos:
      const from = "ãàáäâẽèéëêìíïîõòóöôùúüûñç·/_,:;";

      // Lista de caracteres que serão adicionados em relação aos anteriores:
      const to   = "aaaaaeeeeeiiiiooooouuuunc------";

      // Substitui todos os caracteres especiais:
      for (let i = 0, l = from.length; i < l; i++) {
        str = str.replace(new RegExp(from.charAt(i), 'g'), to.charAt(i));
      }

      // Remove qualquer caractere inválido que possa ter sobrado no texto:
      str = str.replace(/[^a-z0-9 -]/g, '');

      // Substitui os espaços em branco por hífen:
      str = str.replace(/\s+/g, '-');

      return str;
};

//Function SlugFy
